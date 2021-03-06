---
title: Campaign Classic deprecated and removed features
description: This page lists deprecated and removed features of Adobe Campaign Classic
page-status-flag: never-activated
uuid: 
contentOwner: simonetn
products: SG_CAMPAIGN/CLASSIC
audience: rn
content-type: reference
topic-tags: campaign-classic-deprecated-features
discoiquuid: 

internal: n
snippet: y
---

# Deprecated and removed features {#deprecated-and-removed-features}

Adobe constantly evaluates product capabilities to identify older features that should be replaced with more modern alternatives to improve overall customer value, always under careful consideration of backward compatibility. As Adobe Campaign Classic works with 3rd party tools, compatibility is updated on a regular basis, in order to implement supported versions only. Versions which are no longer compatible with Adobe Campaign Classic are listed below.

To communicate the impending removal/replacement of Campaign Classic capabilities, the following rules apply:

* Announcement of deprecation comes first. While deprecated capabilities can still be available for existing users, they will not be further enhanced, nor documented. 
* Removal of deprecated capabilities will occur in the following release at the earliest. Actual target date for removal is announced in this page. 

This process gives customers at least one release cycle to adapt their implementation to a new version or successor of a deprecated capability, before actual removal. 

>[!NOTE]
>Adobe Campaign releases and new capabilities are listed in the [Release Notes](../../rn/using/latest-release.md).


## Deprecated features {#deprecated-features}

This section lists features and capabilities that have been marked as deprecated with latest Campaign Classic releases. 

Generally, features that are planned to be removed in a future release are set to deprecated first, with an alternative provided. These features and capabilities are either no longer available for new Campaign Standard customers, or should not be used for any new implementation. They are also removed from product documentation.

Customers are advised to review if they make use of the feature/capability in their current deployment, and make plans to change their implementation to use the alternative provided. Please refer to the target removal date to plan your environment and project updates accordingly.

### Adobe Campaign 18.6 release {#ac-18-6-release}

<table> 
 <tbody> 
  <tr> 
   <td><strong>Area</strong></td>
   <td><strong>Feature</strong></td> 
   <td><strong>Replacement</strong></td> 
  </tr> 
   <tr> 
   <td>Javascript SDK Security<br>&nbsp;</td>
   <td>decryptString<br>&nbsp;</td>
   <td><p>For security reasons, <em>decryptString</em> API is no longer available by default for new installations.</p> 
   <p>In the context of a postupgrade to 18.6 (and later), this API is no longer activated, and has been replaced by the <em>decryptPassword</em> function.</p><br>&nbsp;</td>
  </tr> 
 </tbody> 
</table>

### Adobe Campaign 18.4 release {#ac-18-4-release}

<table> 
 <tbody> 
  <tr> 
   <td><strong>Area</strong></td>
   <td><strong>Feature</strong></td> 
   <td><strong>Replacement</strong></td> 
  </tr> 
   <tr> 
   <td>Email archiving<br>&nbsp;</td>
   <td>File-based archiving<br>&nbsp;</td>
   <td><p>Email archiving is now available through a dedicated BCC email address. <a href="../../installation/using/email-archiving.md">Learn more</a>.</p> 
   <p><em>Target removal date: Campaign 20.2 release - June 2020</em></p><br>&nbsp;</td>
  </tr> 
   <tr> 
   <td>Lead management<br>&nbsp;</td>
   <td>Leads<br>&nbsp;</td>
   <td><p>The Leads Management package in Adobe Campaign Classic simplified the process of building and maintaining the entire leads management life cycle. Similar functionality can be implemented via other native workflow activities and data model modifications.</p> 
   <p><em>Target removal date: Campaign 20.2 release - June 2020</em></p><br>&nbsp;</td>
  </tr> 
 </tbody> 
</table>


## Deprecated compatibility {#deprecated-compatibility}

### Adobe Campaign 20.1 release {#compat-20-1-release}

Starting 20.1 February Release, the following system is deprecated for Campaign Classic. Compatibility will end in 20.2 release - June 2020.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Area</strong></td>
   <td><strong>Replacement</strong></td> 
  </tr> 
   <tr> 
   <td>Campaign Classic Client Console 32 bits<br>&nbsp;</td>
   <td><p>Campaign Classic Client Console 64 bits</p><br>&nbsp;</td>
  </tr> 
 </tbody> 
</table>

### Adobe Campaign 19.2 release  {#compat-19-2-release}

Starting 19.2 Fall Release, the following operating systems are deprecated for Campaign Classic. Compatibility will end in 2020 EOY.

* Web Server: Apache 2.2. [Learn more](https://wiki.centos.org/About/Product)
* Operating System: CentOS 6. [Learn more](https://wiki.centos.org/About/Product)

Please refer to the [Compatibility matrix](https://helpx.adobe.com/campaign/kb/compatibility-matrix.html) to upgrade to a newer version or move to a new system.

## Removed features {#removed-features}

This section lists features and capabilities that have been removed from Campaign Standard.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Area - Feature</strong></td>
   <td><strong>Replacement</strong></td> 
   <td><strong>Version</strong></td> 
  </tr> 
   <tr> 
   <td>Campaign APIs documentation - jsapi.chm file<br>&nbsp;</td>
   <td>Campaign Classic APIs are now available in a dedicated page. If you were using the jsapi.chm file, you should now refer to <a href="https://docs.adobe.com/content/help/en/campaign-classic/technicalresources/api/index.html">the new online version</a>.</td>
   <td>19.1</td>
  </tr> 
  <tr> 
   <td>Campaign Orchestration - Predictive marketing</td>
   <td>A large part of predictive marketing capabilities in Adobe Campaign Classic has been the consumption of predictive models. Although the predictive marketing workflow activity will be removed in an upcoming version, Adobe Campaign will continue to support the consumption and use of predictive models from external sources through other workflow activities.</td>
   <td>18.10</td>
  </tr> 
  <tr> 
   <td>Web applications - Microsites</td>
   <td>Improve security by restricting access to only dedicated domains on Adobe Campaign configuration files. You can still use personalized URLs in Campaign by using DNS aliases. <a href="https://helpx.adobe.com/campaign/kb/domain-name-delegation.html">Learn more</a>.</td>
   <td>18.10</td>
  </tr> 
  <tr> 
   <td>Push Notifications - iOS Binary Connector<br>&nbsp;</td>
   <td>Per Apple's recommendation, Adobe will be removing the legacy iOS Binary Connector. The more capable and more efficient HTTP/2-based connector is already available.</td>
   <td>18.10</td>
  </tr> 
   <tr> 
   <td>Mobile channel - MMS and WAP Push messages</td>
   <td>MMS and Wap Push channels are no longer available. As a replacement, you can leverage <a href="../../delivery/using/sms-channel.md">SMS</a> and <a href="../../delivery/using/about-mobile-app-channel.md">Push</a> deliveries.</td>
   <td>18.4</td>
  </tr> 
   <tr> 
   <td>Mobile channel - LINE v1</td>
   <td>LINE Connect package is no longer available for installation in Adobe Campaign Classic. Adobe recommends using the new LINE Channel package to send LINE messages. <a href="../../delivery/using/line-channel.md">Learn more</a>.</td>
   <td>18.4</td>
  </tr> 
 </tbody> 
</table>

## End of compatibility {#end-of-compatibility}

>[!CAUTION]
>
>Adobe Campaign Classic is compatible with all the systems and tools listed in the [Compatibility matrix](https://helpx.adobe.com/campaign/kb/compatibility-matrix.html). When specific versions of these 3rd party systems and tools reach end-of-life (EOL) with their respective creators, Adobe Campaign is no longer compatible with those versions: they are announced as deprecated, and then are removed from our compatibility matrix in the subsequent product release. Please ensure you are on supported versions of any systems listed in the compatibility matrix to avoid any issues.

### Client console {#client-console-eol}

Adobe Campaign Classic Client Console can no longer run on the following systems as they have been deprecated by their editor. Customers running Campaign Client Console on one of these versions need to upgrade to newest version before target removal date. Refer to the [Compatibility matrix](https://helpx.adobe.com/campaign/kb/compatibility-matrix.html).

* Windows Server 2003, 2008, 2008 R2
* Windows XP, Vista

### Operating systems {#o-s-eol}

Starting 19.1 release, Adobe Campaign is no longer compatible with the following operating systems.

* Debian 7. [Learn more](https://wiki.debian.org/DebianReleases).
* RHEL 6.x. [Learn more](https://access.redhat.com/support/policy/updates/errata).
* Windows Server 2008. [Learn more](https://support.microsoft.com/en-us/lifecycle/search/1163).
* SLES 11. [Learn more](https://www.suse.com/lifecycle).

### Web servers {#web-server-eol}

Starting 19.1 Spring Release, Adobe Campaign is no longer compatible with the following web server. 

* Microsoft IIS 7. [Learn more](https://support.microsoft.com/en-us/lifecycle/search/810).

### Tools {#tools-eol}

Starting 19.1 Spring Release, Adobe Campaign is no longer compatible with the following tools.

* Java JDK 7. [Learn more](http://www.oracle.com/technetwork/java/javase/eol-135779.html).
* Libre Office 3.5 / 4.3 / 5.x, except when embeded in another tool. [Learn more](https://wiki.documentfoundation.org/ReleasePlan/Archive#End-of-Life_Releases).

### Database engines {#dbe-eol}

Adobe does not support the following database engines as they have been deprecated by their editor. Customers running in these versions need to upgrade to newest version or move to another one.

Refer to [Campaign Classic Compatibility matrix](https://helpx.adobe.com/campaign/kb/compatibility-matrix.html) to access the list of compatible versions.

**FEDERATED DATA ACCESS (FDA)**

Starting 19.1 Spring Release, Adobe Campaign is no longer compatible with the following FDA Servers.

* Oracle 11G. [Learn more](http://www.oracle.com/us/support/library/lifetime-support-technology-069183.pdf).
* PostgreSQL 9.3. [Learn more](https://www.postgresql.org/support/versioning).
* MySQL 5.5. <[Learn more](http://www.fromdual.com/support-for-mysql-from-oracle).
* DB2 9.5. [Learn more](http://www-01.ibm.com/support/docview.wss?uid=swg21168270).
* Teradata 14 – 14.1. [Learn more](https://community.teradata.com/t5/Database/Teradata-Database-Product-Life-Cycle/td-p/35068).

Campaign Classic is not compatible with the following servers in Federated Data Access (FDA).

* DB2 UDB 9.5, 9.7. More recent version of DB2 is supported through Federated Data Access (FDA). [Learn more](http://www-01.ibm.com/support/docview.wss?uid=swg21168270).
* Oracle 9i, 10G R2. More recent versions of Oracle are supported through Federated Data Access (FDA). [Learn more](http://www.oracle.com/us/support/library/lifetime-support-technology-069183.pdf).
* PostgreSQL 8.3, 8.4, 9.0, 9.1, 9.2. More recent versions of PostgreSQL are supported through Federated Data Access (FDA). [Learn more](https://www.postgresql.org/support/versioning).
* MSSQL 2000, 2005, 2008 R2. More recent versions of SQL Server are supported through Federated Data Access (FDA). [Learn more](https://support.microsoft.com/en-us/lifecycle/search/1044).
* MySQL 5.1. More recent versions of MySQL are supported through Federated Data Access (FDA). [Learn more](https://en.wikipedia.org/wiki/InfiniDB).
* InfiniDB reached end of life. [Learn more](https://www.mysql.com/support).
* Teradata 13, 13.1. More recent versions of Teradata are supported through Federated Data Access (FDA). [Learn more](https://www.info.teradata.com/download.cfm?ItemID=1007255).
* Netezza 6.02, 7.0. Netezza reached end of life. [Learn more](https://en.wikipedia.org/wiki/Netezza).
* AsterData 5.0. AsterData reached end of life. [Learn more](https://en.wikipedia.org/wiki/Aster_Data_Systems).
* Sybase IQ 15.2, 15.4, 15.5 and Sybase ASE 15.0. More recent versions of Sybase are supported through Federated Data Access (FDA). [Learn more](https://sites.google.com/site/dbatipsandtricks/time-tracker).
* Hadoop via HiveSQL: Hadoop 2.7.3, HiveSQL 1.2.1. Adobe Campaign Classic will still support the listed versions of Hadoop via HiveSQL through Federated Data Access (FDA), but these versions are merged with: HortonWorks (HDP 2.4.X, 2.5.x, 2.6.x) and HDInsight 3.4 (HDP 2.4), 3.5 (HDP 2.5), 3.6 (HDP 2.6)

**RDBMS SERVER**

Adobe Campaign is not compatible with the following RDBMS Servers:
* Oracle 10GR2, 11G
* PostgreSQL 9.0 to 9.3
* SQL Server 2005
* MySQL 5.1
* DB2 UDB 9.7
