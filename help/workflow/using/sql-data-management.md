---
title: SQL Data Management
seo-title: SQL Data Management
description: SQL Data Management
seo-description: 
page-status-flag: never-activated
uuid: 6eac1c9f-2a23-4ae5-ab77-1da1c3a8040d
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
content-type: reference
discoiquuid: 0be4f2cc-1acd-44ec-8812-966e0017eff2
index: y
internal: n
snippet: y
---

# SQL Data Management{#sql-data-management}

The **SQL Data Management** activity lets you write your own SQL scripts to create and populate work tables.

## Prerequisites {#prerequisites}

Before configuring the activity, make sure the following prerequisites are fulfilled:

* The activity is available for remote data sources only. The **FDA** (Federated Data Access) package must therefore be installed on your instance (see [this section](../../platform/using/accessing-an-external-database.md)).
* The Outbound schema must exist in the database and be linked to an FDA database (for more on data schemas, refer to [this section](../../configuration/using/about-schema-reference.md)).
* The operator executing the workflow must have the **USE SQL DATA MANAGEMENT ACTIVITY (useSqlDmActivity)** named right. For more on named rights, refer to [this section](../../platform/using/access-management.md#named-rights).

## Configuring the SQL Data Management activity {#configuring-the-sql-data-management-activity}

1. Specify the activity **Label**.
1. Select the **External account** to use, then select the **Outbound schema** linked to this external account.

   >[!CAUTION]
   >
   >The Outbound schema is fixed and cannot be edited.

1. Add the SQL script.

   >[!CAUTION]
   >
   >It is the SQL script writer's responsibility to make sure that the SQL script is functional, and that its references (fields names, etc.) are in accordance with the Outbound schema.

   If you want to load an existing SQL code, select the **The SQL script is contained in an entity stored in the database** option. SQL scripts must be created and stored in the **Administration** / **Configuration** / **SQL scripts** menu.

   Otherwise, type or copy-paste your SQL script in the dedicated area.

   ![](assets/sql_datamanagement.png)

   The activity lets you use the following variables in the script:

    * **activity.tableName**: SQL name of the outbound work table.
    * **task.incomingTransitionByName(‘name’).tableName**: SQL name of the work table carried by the incoming transition to use (the transition is identified by its name).

      >[!NOTE]
      >
      >The ('name') value corresponds to the **Name** field from the transition properties.

1. If the SQL script already contains commands to create an outbound work table, unselect the **Automatically create work table** option. Otherwise, a work table is automatically created once the workflow executes.
1. Click **Ok** to confirm the activity configuration.

The activity is now configured. It is ready to be executed in the workflow.

>[!CAUTION]
>
>Once the activity executed, the outbound transition records count is indicative only. It may vary according to the level of complexity of the SQL script.   
>If the activity is restarted, the whole script is executed from its beginning, regardless of it execution status.

## SQL script samples {#sql-script-samples}

>[!NOTE]
>
>The script samples in this section are meant to be executed under PostgreSQL.

Below script lets you create a work table and insert data into this same work table:

```
CREATE UNLOGGED TABLE <%= activity.tableName %> (
  iRecipientId INTEGER DEFAULT 0,
  sFirstName VARCHAR(100),
  sMiddleName VARCHAR(100),
  sLastName VARCHAR(100),
  sEmail VARCHAR(100)
);

INSERT INTO <%= activity.tableName %>
SELECT iRecipientId, sFirstName, sMiddleName, sLastName, sEmail
FROM nmsRecipient
GROUP BY iRecipientId, sFirstName, sMiddleName, sLastName, sEmail;
```

Below script lets you perform a CTAS operation (CREATE TABLE AS SELECT) and create a work table index:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT iRecipientId, sEmail, sFirstName, sLastName, sMiddleName
FROM nmsRecipient
WHERE sEmail IS NOT NULL
GROUP BY iRecipientId, sEmail, sFirstName, sLastName, sMiddleName;

CREATE INDEX ON <%= activity.tableName %> (sEmail);

ANALYZE <%= activity.tableName %> (sEmail);
```

Below script lets you merge two working tables:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```
