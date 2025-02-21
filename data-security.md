---

copyright:
  years: 2019, 2022
lastupdated: "2021-08-09"

keywords: IBM Cloud, Activity Tracker, auditing, overview, personal data, data deletion, PHI, data, data security, _service-name_

subcollection: activity-tracker


---

{{site.data.keyword.attribute-definition-list}}


# Securing your data
{: #mng-data}

To ensure that you can securely manage your data when you use {{site.data.keyword.atracker_full_notm}}, it is important to know exactly what data is stored and encrypted, and how you can delete any stored personal data.
{: shortdesc}


## What data is stored in {{site.data.keyword.atracker_full_notm}}
{: #data-stored}

{{site.data.keyword.atracker_full_notm}} collects management and data events from {{site.data.keyword.cloud_notm}} services and resources: 
* **Management Events** are generated when an API call changes the state of a Cloud resource. A resource might be an entire service instance or a resource managed by the service. 
* **Data Events** are generated when an API call reads or modifies a resource's data. 

Data from [{{site.data.keyword.cloud_notm}} services and resources](/docs/services/activity-tracker?topic=activity-tracker-cloud_services) is collected automatically.  However, some services might require an upgrade of the service plan, a configuration setting, or both, for you to be able to collect and analyze them.


## How your data is stored and encrypted in {{site.data.keyword.atracker_short}}
{: #data-storage}

Data is hosted on the {{site.data.keyword.cloud_notm}}. 

Events can be classified as global or location-based. [Learn more](/docs/services/activity-tracker?topic=activity-tracker-event_types).
* **Location-based events** maintain data locality to the services that run in that Cloud location.
* **Global events** are collected and made available through the region in your account that you configure to collect global auditing events for {{site.data.keyword.atracker_short}} event routing. **Global events** are collected and made available through the {{site.data.keyword.at_full_notm}} instance that is configured in Frankfurt for {{site.data.keyword.at_short}} hosted event search offerings.


### How your data is stored and encrypted in {{site.data.keyword.atracker_short}} event routing
{: #data-storage-atracker}

You must configure where events are stored in your account. You can route auditing events from different regions to buckets in {{site.data.keyword.cos_full_notm}} in your account. To collect auditing events in your account, you must define 1 or more targets, and 1 or more routes to specify where the auditing events that are collected in the account must be stored. You define 1 target and 1 route per region. 

{{site.data.keyword.atracker_full_notm}} does not store auditing events. You manage the bucket and the data that is uploaded by {{site.data.keyword.atracker_full_notm}} in your account. 

The configuration of targets and routes is done via REST API calls. 

If you delete a target or a route, the configuration is deleted, and the routing of auditing events that is affected by the deletion interrupted.

To ensure that you have enhanced control and security over your data, your account must be virtual routing and forwarding (VRF) enabled and you must use private routes to {{site.data.keyword.cloud}} service endpoints. When you configure a target and a route in {{site.data.keyword.atracker_full_notm}}, you must configure these resources over a private network connection. Auditing data from an {{site.data.keyword.cloud_notm}} service to your target service in {{site.data.keyword.cloud_notm}} is secure via private connection. The connection supports TLS 1.2.

{{site.data.keyword.atracker_full_notm}} stores the configuration of targets and routes for your account. 
- Connections use TLS/SSL encryption for data in transit. The current supported version of this encryption is TLS 1.2.
- The storage where the configuration is stored is encrypted with LUKS using AES-256. 

Auditing events are stored in a {{site.data.keyword.cos_full_notm}} bucket. You create and manage the bucket, and the data that is collected in the bucket. For more information about COS data security, see [Data security](/docs/cloud-object-storage?topic=cloud-object-storage-security).




### How your data is stored and encrypted in {{site.data.keyword.at_short}} hosted event search offerings
{: #data-storage-at}

{{site.data.keyword.at_full_notm}} collects and aggregates logs. 

- All the data that is hosted in an auditing instance is encrypted at rest using **AES 256**.

- When an {{site.data.keyword.cloud_notm}} service sends data to an auditing instance, data is encrypted in transit over HTTPS.

- When a user requests an export, the data is encrypted during transit, and is also encrypted at rest in {{site.data.keyword.cos_full_notm}} (COS).

The service plan that you choose for an {{site.data.keyword.at_full_notm}} instance defines the number of days that data is stored and retained. For example, if you choose the *Lite* plan, data is not stored at all. However, if you choose the 7-day plan, data is stored for 7 days and you have access to it through the UI.

You can archive events from an {{site.data.keyword.at_full_notm}} instance into a bucket in an {{site.data.keyword.cos_full_notm}} (COS) instance. [Learn more](/docs/services/activity-tracker?topic=activity-tracker-archiving). When data is archived, data going to {{site.data.keyword.cos_full_notm}} (COS) is encrypted in transit over HTTPS. You must configure archiving to a COS instance if you want to backup your events for long term storage. You can use the {{site.data.keyword.sqlquery_short}} service to query data in archive files that are stored in an {{site.data.keyword.cos_short}} (COS) bucket in your account. You can run queries from the {{site.data.keyword.cloud_notm}} UI, or programmatically.

You can export data in JSONL format locally, write data to your terminal, or request an email with a link to the data. [Learn more](/docs/services/activity-tracker?topic=activity-tracker-export). Consider the following information when you export log data:
* You export a set of event entries. To define the set of data that you want to export, you can apply filter and searches. You can also specify the time range. 
* From the Web UI, when you export events, you get an email that is sent to your email address, with a link to a compressed file that includes the data. To get the data, you must click the link and download the compressed file. Notice that the link expires automatically after 12 hours. The compressed file is hosted in {{site.data.keyword.cos_full_notm}} (COS).
* When you export data, you have a limit of lines that you can export in a request. You can specify to export older lines or newer lines in case you reach the limit in the time range that you specify for the export.

When you delete an instance, the instance is automatically deactivated, and ingestion of events is stopped. [Learn more](/docs/services/activity-tracker?topic=activity-tracker-remove). {{site.data.keyword.at_short}} deletes all events that are already ingested. Deletion is completed within 24 hours after receiving your request. You are responsible for managing archived data. 

When you delete an auditing instance, user metadata such as views, alerts, dashboards, screens, and templates, is never deleted. You must open a case through support to request the data to be deleted. For more information, see [Open a support ticket](/docs/get-support). You are responsible for deleting archived metadata. 

You can delete metadata such as views, dashboards, screens, templates, and alerts at any time.

Deletion of a subset of your data is not supported. For example, you cannot delete data for a specific service. You cannot delete data that match a particular query.

