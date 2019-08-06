---
title: Interaction best practices
seo-title: Interaction best practices
description: Interaction best practices
seo-description: 
page-status-flag: never-activated
uuid: c5f3029d-8fbe-431d-b2a8-3c7ac27e9890
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: interaction
content-type: reference
discoiquuid: a8f868ee-aadd-4848-9538-fb2229c6aa46
index: y
internal: n
snippet: y
---

# Interaction best practices{#interaction-best-practices}

## General recommendations {#general-recommendations}

This chapter presents the best practice approach to manage the Interaction module in Adobe Campaign Classic, including eligibility rules, pre-defined filters, workflow activities and database options.

Interaction in Adobe Campaign requires careful management to operate efficiently. You must find a balance between the number of contacts and the number of offer categories and offers. If those factors are not dealt carefully, your Adobe Campaign instance may encounter issues.

## Implementation {#implementation}

Below are listed important elements that should be kept in mind when implementing and configuring interactions.

* For batch engine (typically used in outbound communications like email), throughput is the main concern, as multiple contacts can be handled at the same time. The typical bottleneck is database performance.
* The main constraint for unitary engine (typically used in inbound communications like a banner on a web site) is latency, as someone is expecting an answer. The typical bottleneck is CPU performance.
* The offer catalogue design has a huge impact on Adobe Campaign Classic performance.

## Eligibility rules {#eligibility-rules}

Below are listed some best practices regarding eligibility rules.

* Simplify the rules. Rules complexity impacts performance as it extends the look-up. A complex rule is any rule that has more than five conditions.
* To increase performance, rules can be broken out in distinct predefined filters that are shared across multiple offers.
* Put the most restrictive offer category rules at the highest possible position in the tree. Doing this, they will filter out the most contacts first, reducing the target number and preventing them from being processed by further rules.
* Put the most expensive rules in terms of time or processing at the bottom of the tree. Doing this, these rules will only be run on the remaining target audience.
* Start at a specific category to avoid scanning the whole tree.
* To save processing time, precompute aggregates instead of building complex rules with joins. To do this, try to store customer data in a reference table that can be looked up within eligibility rules.
* Use a minimum number of weights to limit the number of queries.
* It is recommended having a limited number of offers per offer space. This ensures faster retrieval of offers in any given space.
* Use indexes, especially on frequently used look-up columns.

## Proposition table {#proposition-table}

Below are listed a few best practices regarding the proposition table.

* Use a minimum number of rules to make the processing as fast as possible.
* Limit the number of records in the proposition table: only keep the records that are needed to track its status update and what is needed by the rules, then archive them into another system.
* Perform intensive database maintenance on the proposition table, such as rebuild indexes or recreate table.
* Limit the number of propositions asked per target. Do not set more than what you are actually going to use.
* Avoid joins as much as possible in the rule criteria.
