---

copyright:
  years: 2019, 2022
lastupdated: "2021-08-09"

keywords: IBM Cloud, LogDNA, Activity Tracker, getting started, auditing, PagerDuty

subcollection: activity-tracker

---

{{site.data.keyword.attribute-definition-list}}

# Integrating with PagerDuty
{: #pagerduty}


You can send alerts to PagerDuty. 
{: shortdesc}

This information applies only if you use an {{site.data.keyword.at_full}} [hosted event search offering](/docs/activity-tracker?topic=activity-tracker-service_plan).
{: important}

## Configuring PagerDuty
{: #pagerduty-config}

When you [configure an alert](/docs/activity-tracker?topic=activity-tracker-alerts#configure-an-alert), you can have that alert sent to PagerDuty.

1. When configuring your alert, click ![PagerDuty icon](images/pagerduty.png "PagerDuty icon").

2. Select if you want the alert to be sent when the condition exists (**Presence**) or does not exist (**Absence**).

3. Indicate the logging criteria when an alert should be sent.  For example, when 100 lines matching in the view are logged in an hour.  A graph will help you determine the number of log lines matching your specified criteria.

4. Select if the alert should be sent at the end of the selected period or immediately when the number of lines are logged.

5. Optionally you can specify a **Custom schedule** with alerting limited to a specified timezone, days of the week, or timeframe. To configure a **Custom schedule**:

    1. Select **on** for **Custom schedule**.
    2. Select the Timezone for the log entries. 
    3. Select the days of the week when alerts should be generated.
    4. Optionally specify a time range for the selected days. A graph will help you determine the number of log entries for the timezone and time range.

6. Specify the **Service**. If required, you will be prompted to connect to PagerDuty.  

    If no services are listed, click **Add PagerDuty** to connect and add a service. Create a PagerDuty service and associate it with an escalation policy. You will be directed to PagerDuty to authorize the integration. After authorization, your alerts will display in the PagerDuty incidents dashboard.

7. Optional: You can click **Test** to test that your alert configuration is correct.

   ![PagerDuty Test button](images/pagerduty-test.png "PagerDuty Test button")

8. Click **Save Alert**.

   The alert definition must be saved for alerts to be sent to PagerDuty.
   {: important}

## Integrating with multiple PagerDuty services

Each view can be linked to one or more PagerDuty services.  To alert multiple PagerDuty accounts, configure multiple alerts for the same view with each alert notifying a different PagerDuty account.

You can also configure differnt views to notify a single PagerDuty account.

## Limitations
{: #pagerduty-limitations}

Due to [PagerDuty API limitations](https://developer.pagerduty.com/docs/events-api-v2/overview/){: external}, all requests are trimmed to a maximum of 400 KB.

