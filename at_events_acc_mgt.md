---

copyright:
  years: 2019, 2020
lastupdated: "2020-08-10"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events, catalog, tags

subcollection: Activity-Tracker-with-LogDNA

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}

# Auditing events for account management  
{: #at_events_acc_mgt}

As a security officer, auditor, or manager, you can use the {{site.data.keyword.at_full_notm}} service to track how users and applications interact with an {{site.data.keyword.cloud}} account. 
{:shortdesc}

The {{site.data.keyword.at_full_notm}} service records user-initiated activities that change the state of a service in {{site.data.keyword.cloud_notm}}. To get started, see [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=Activity-Tracker-with-LogDNA-getting-started#getting-started). 



## Events for managing accounts
{: #at_events_acc_mgt_account}

The following table lists the actions that generate an event:

| Action                               | Description |
|--------------------------------------|-------------|
| `billing.account.create`             | An event is generated when you create an account after the account ID is assigned to the account. |
| `billing.account.update`             | An event is generated when you update information about the account.  |
| `billing.account.active`             | An event is generated when you verify the account, that is, an event is generated when the account becomes active. |
| `billing.account-subscription.create` | An event is generated when you create a [Subscription account](/docs/account?topic=account-accounts#subscription-account) </br><a href="/docs/account?topic=account-accounts#subscription-account">Subscription account</a>. |
{: caption="Table 1. Actions that generate account management events" caption-side="top"} 


## Events for managing account usage reports
{: #at_events_acc_mgt_account_reporst}

These events are generated when a user looks at usage information in the account. For example, the user can look at usage data through the **Manage** &gt; **Billing and usage** &gt; **Usage** section, or request an export of the data. Also, users can request usage information through the CLI or by making direct [API calls](/apidocs/metering-reporting#introduction). 


### Events for managing single account usage reports
{: #at_events_acc_mgt_account_reporst_std}

The following table lists the actions that generate an event:

| Action                                               | Description |
|------------------------------------------------------|-------------|
| `billing.account-summary.read`                       | An event is generated when a user views the account level summary usage page that is displayed by default. |
| `billing.account-summary.download`                   | An event is generated when a user requests a **summary** export of the data in csv format from the account level summary usage page. |
| `billing.account-usage-report.read`                  | An event is generated when a user views the usage data that is displayed after the user configures a time frame, a resource group, or both in the default account level summary usage page. This event is also generated when a user views the instances usage data page. |
| `billing.account-instances-usage-report.download`    | An event is generated when a user requests an **instances** export of the data in csv format from the account level summary usage page. |
{: caption="Table 2. Actions that generate account management events" caption-side="top"} 


### Events for managing enterprise usage reports
{: #at_events_acc_mgt_reporst_enterprise}

The following table lists the actions that generate an event:

| Action                                               | Description |
|------------------------------------------------------|-------------|
| `billing.enterprise-usage-report.read`               | An event is generated when a user views the enterprise account level summary usage page that is displayed by default. |
| `billing.enterprise-usage-report.download `          | An event is generated when a user requests a **summary** export of the data in csv format from the enterprise account level summary usage page.  |
| `billing.enterprise-instances-usage-report.download` | An event is generated when a user requests an **instances** export of the data in csv format from the enterprise account level summary usage page. |
{: caption="Table 3. Actions that generate account management events" caption-side="top"} 


## Events for managing IAM account settings
{: #at_events_acc_mgt_acc_iam}

The following table lists the actions that generate an event when an account setting that is controlled from the **Manage** &gt; **Access IAM** &gt; **Settings** dashboard is modified:

| Action                               | Description |
|--------------------------------------|-------------|
| `billing.account-traits.update`      | An event is generated when an account setting is modified. |
| `billing.account-mfa.set-on`         | An event is generated when the `Account Login` setting sets on multifactor authentication in the account. |
| `billing.account-mfa.set-off`        | An event is generated when the `Account Login` setting sets off multifactor authentication in the account. |
{: caption="Table 4. Actions that generate events when the account settings are changed" caption-side="top"} 


## Events for managing catalogs
{: #at_events_catalog_management}

The following tables list the actions that generate an event:

### Events for managing catalogs
{: #at_events_catalog_1}

| Action                                           | Description                                                           | 
|--------------------------------------------------|-----------------------------------------------------------------------|
| `globalcatalog-collection.instance.read`           | An event is generated when you view a catalog.            | 
| `globalcatalog-collection.instance.update`         | An event is generated when you update a catalog.          |
| `globalcatalog-collection.instances.list`           | An event is generated when you get a list of the catalogs in an account.           | 
{: caption="Table 5. Actions that generate catalog management events" caption-side="top"}

### Events for managing products in a catalog
{: #at_events_catalog_2}

| Action                                           | Description                                                           | 
|--------------------------------------------------|-----------------------------------------------------------------------|
| `globalcatalog-collection.offerings.list`         |  An event is generated when you get a list of the products in a catalog.          |
| `globalcatalog-collection.offering.read`           | An event is generated when you view a product in a catalog.            |
| `globalcatalog-collection.offering.create`         | An event is generated when you create a product.          |
| `globalcatalog-collection.offering.update`         | An event is generated when you update a product.          |
| `globalcatalog-collection.offering.delete`         | An event is generated when you delete a product.          |
{: caption="Table 6. Actions that generate product catalog management events" caption-side="top"}

### Events for managing account settings that are related to catalogs
{: #at_events_catalog_3}

| Action                                           | Description                                                           | 
|--------------------------------------------------|-----------------------------------------------------------------------|
| `globalcatalog-collection.account-settings.read`   | An event is generated when you view the account settings.   | 
| `globalcatalog-collection.account-settings.update` | An event is generated when you update the account settings. |
{: caption="Table 7. Actions that generate account settings management events" caption-side="top"}

### Events for managing enterprise account settings that are related to catalogs
{: #at_events_catalog_4}

| Action                                           | Description                                                           | 
|--------------------------------------------------|-----------------------------------------------------------------------|
| `globalcatalog-collection.enterprise-settings.read` | An event is generated when you view the enterprise settings. |
| `globalcatalog-collection.enterprise-settings.update` | An event is generated when you update the enterprise settings. |
| `globalcatalog-collection.enterprise-settings.list` | An event is generated when you get a list of the enterprises in an account and their corresponding settings. | 
{: caption="Table 8. Actions that generate enterprise account settings management events" caption-side="top"}

### Events for managing license and entitlement events
{: #at_events_catalog_entitlement}

The following table lists the actions that generate an event:

| Action                                 | Description |
|----------------------------------------|---------|
| `entitlement.entitlement.create`       | An event is generated when an initiator binds a license to an account. |  
| `entitlement.entitlement.delete`       | An event is generated when an initiator deletes an entitlement. |  
| `entitlement.entitlement.delete_purge` | An event is generated when an initiator purges an entitlement. |
| `entitlement.entitlement.update`       | An event is generated when an initiator updates an entitlement. |
| `entitlement.entitlement.check`        | An event is generated when an initiator uses an entitlement to pull an image from the governed IBM Container Registry. |
| `entitlement.entitlement.invalidate`   | An event is generated when an entitlement's license is not valid anymore. |
{: caption="Table 9. User entitlement actions" caption-side="top"}

## Events for managing organizations
{: #at_events_acc_mgt_org}

The following table lists the actions that generate an event:

| Action                               | Description |
|--------------------------------------|-------------|
| `billing.account-org.create`         | An event is generated when you add an organization to the account. |
{: caption="Table 10. Actions that generate events" caption-side="top"} 


## Events for managing tags
{: #at_events_acc_mgt_resources}

The following table lists the actions that generate an event:

| Action                                          | Description |
|-------------------------------------------------|-------------|
| `global-search-tagging.tag.attach`              | An event is generated when you associate a tag to a resource. |
| `global-search-tagging.tag.detach`              | An event is generated when you remove a tag from a resource.  |
| `global-search-tagging.tag.update`              | An event is generated when you update a tag that is attached to a resource.  |
| `global-search-tagging.tag.delete`              | An event is generated when you delete a tag in your account.  |
| `global-search-tagging.tags.delete`             | An event is generated when you delete all the tags that are not attached to resources in your account.  |
{: caption="Table 11. Actions that generate events" caption-side="top"} 


## Events for managing users
{: #at_events_acc_mgt_users}

The following table lists the actions that generate an event:

| Action                               | Description |
|--------------------------------------|-------------|
| `user-management.user.create`        | An event is generated when you invite a user to the account. |
| `billing.user.active`                | An event is generated when a user, that has received an email invitation to join an account, verifies the email address. |
| `user-management.user.update`        | An event is generated when log in configurations are modified for a user from the {{site.data.keyword.cloud_notm}} UI. |
| `user-management.user.delete`        | An event is generated when you remove a user from the account. |
| `user-management.user-setting.update` | An event is generated when you update the user's login configuration settings: User one-time passcode authentication ,Require MFA security questions at login, User-managed login or Setting up security questions |
{: caption="Table 12. Actions that generate events" caption-side="top"} 


## Where to look for the events
{: #at_events_acc_mgt_ui}

Events are available in the **Frankfurt (eu-de)** region. 

To view these events, you must [provision an instance](/docs/services/Activity-Tracker-with-LogDNA?topic=Activity-Tracker-with-LogDNA-provision#provision) of the {{site.data.keyword.at_full_notm}} service in the **Frankfurt (eu-de)** region. Then, you must [open the {{site.data.keyword.at_full_notm}} UI](/docs/Activity-Tracker-with-LogDNA?topic=Activity-Tracker-with-LogDNA-launch#launch_cloud_ui). 


## Analyzing events
{: #at_events_analyze}

### Account IAM settings events
{: #at_events_analyze_1}

This section explains events that are generated when you configure the IAM account settings from the **Access (IAM)** &gt; **Settings** dashboard.

#### Configuring MFA
{: #at_events_analyze_1_1}

When you set on MFA in your account by configuring the **Account Login** section in the **Access (IAM)** &gt; **Settings** dashboard, you get 2 events:
* Event with action `billing.account-traits.update` that reports the type of MFA that is configured in the account in the `requestData.mfa` field.
* Event with action `billing.account-mfa.set-on` that indicates that MFA is enabled in the account.

When you set off MFA, you get the following 2 events:
* Event with action `billing.account-traits.update` that reports the type of MFA that is configured in the account in the `requestData.mfa` field.
* Event with action `billing.account-mfa.set-off` that indicates that MFA is disabled in the account.

For example, see the `requestData` field for the event `billing.account-traits.update`: 

```json
"action": "billing.account-traits.update",
"message": "Billing service: update account traits",
"requestData": {
    "mfa": "",
    "origin": "BSS"
}
```
{: screen}

#### Configuring user list visibility restriction
{: #at_events_analyze_1_2}

When you modify the *User list visibility restriction* IAM account setting in the **Manage** &gt; **Access (IAM)** &gt; **Settings** dashboard, you get 1 event with action `billing.account-traits.update`.

For example, see the `requestData` field for the event `billing.account-traits.update`: 

```json
"action": "billing.account-traits.update",
"message": "Billing service: update account traits",
"requestData": {
    "origin": "BSS",
    "team_directory_enabled": false
}
```
{: screen}

#### requestData fields
{: #at_events_analyze_1_reqdata}

The following table lists *requestData* fields that you can find in events that are generated when the IAM account settings are modified from the **Access (IAM)** &gt; **Settings** dashboard:


| Field | Type | Description |
|-------|------|-------------|
| `team_directory_enabled`   | Boolean         | Defines the status of the *User list visibility restriction* IAM account setting. </br>When it is set to `true`, users in your account can view other users from the Users page. |
| `mfa`                      | String          | Defines the MFA method that is required for users to log in to the account. </br>Valid values are *TOTP*, and *TOTP4ALL* </br>This field is set to `TOTP` when the account requires MFA for non-federated users only. Users are required an ID, password, and a time-based one-time passcode to log in. </br>This field is set to `TOTP4ALL` when the account requires MFA for all users.</br>All users by requiring an ID, password, and a time-based one-time passcode. </br>When this field is empty, MFA is not enabled in the account, and all users log in by using a standard ID and password. |
{: caption="Table 13. Account IAM settings requestData fields" caption-side="top"} 




### Catalog events
{: #at_events_analyze_2}

You can find the value `unavailable` in catalog events. This value indicates when an update is made, but specific details about the update aren't included. 
{: important}



### User management events
{: #at_events_analyze_3}

This section explains events that are generated when you manage users from the **Manage** &gt; **Access IAM** &gt; **Users** dashboard.

When you analyze user management events, `target.name` is set to the user ID of the user on which the action is requested.


#### Modify the status of a user
{: #at_events_analyze_3_1}

When you modify information about the user status from the **User Details** section, you get the following 2 events:
* Event with action `user-management.user.update` that reports a request in the account to modify the user's properties.
* Event with action `user-management.user-setting.update` that indicates the values of the user's properties after the update request completes.

Depending on the request, you might get additional events with action `user-management.user-setting.update`. If your account is a Lite one, you only get 1 event with action `user-management.user.update`.

For example, see the `requestData` field for the event `user-management.user-setting.update`: 

```json
"action": "user-management.user-setting.update",
"message": "User management service: update user settings",
"requestData": {
    "2FA": false,
    "allowed_ip_addresses": "",
    "iam_id": "IBMid-xxxxxxx",
    "origin": "BSS",
    "security_questions_setup": false
}
```
{: screen}

#### Restrict IP addresses
{: #at_events_analyze_3_2}

When you configure IP address restrictions from the **IP address restrictions** section, you get 1 event with action `user-management.user-setting.update`.

For example, see the `requestData` field for the event `user-management.user-setting.update`: 

```json
"action": "user-management.user-setting.update",
"message": "User management service: update user settings",
"requestData": {
    "allowed_ip_addresses": "14.15.98.123",
    "iam_id": "IBMid-xxxxxxx",
    "origin": "BSS"
}
```
{: screen}


#### Manage user's login
{: #at_events_analyze_3_3}

When you modify information about a user's login from the **Manage** &gt; **Access IAM** &gt; **Users** &gt; **User Details** section, you get 1 event with action `user-management.user-setting.update`.

See the sample of the `requestData` field when the **User-managed login:** property is disabled:

```json
"action": "user-management.user-setting.update",
 "message": "User management service: update user settings",
"requestData": {
    "iam_id": "IBMid-27000757DW",
    "origin": "BSS",
    "self_manage": false
}
```
{: screen}


See the sample of the `requestData` field when the **User one-time passcode authentication:** property is enabled. The `requestData.2FA` field is set to `true`.

```json
"action": "user-management.user-setting.update",
"message": "User management service: update user settings",
"requestData": {
    "2FA": true,
    "iam_id": "IBMid-xxxxx",
    "origin": "BSS",
    "security_questions_setup": true,
    "self_manage": false
 }
}
```
{: screen}

See the sample of the `requestData` field when the **Require MFA security questions at login:** property is enabled. The `requestData.security_questions_setup` field is set to `true`.

```json
"action": "user-management.user-setting.update",
"message": "User management service: update user settings",
"requestData": {
    "2FA": true,
    "iam_id": "IBMid-xxxxxx",
    "origin": "BSS",
    "security_questions_setup": true,
    "self_manage": false
 }
}
```
{: screen}




#### requestData fields
{: #at_events_analyze_3_reqdata}

The following table lists *requestData* fields that you can find in events that are generated when user details are modified from the **Users** dashboard:

| Field | Type | Description |
|-------|------|-------------|
| `2FA`                      | Boolean         | Defines the MFA requirements for users in the account. </br>This field is set to `true` when MFA is enabled for users.  | 
| `allowed_ip_addresses`     | String          | List of IP addresses from where a user is allowed to access account resources. |
| `iam_id`                   | String          | Defines the IBM ID of the user whose settings are being modified. |
| `security_questions_setup` | Boolean         | Defines when a user requires security questions to log in to the account. </br>This field is set to `true` to indicate that questions are required.  |
| `self_manage`              | Boolean         | Defines whether a user can configure his log in settings on how to log in to the account.  </br>This field is set to `true` to allow a user to set password expiration, turn on security questions for login, and define allowed IP addresses for log in to {{site.data.keyword.cloud_notm}} and from classic infrastructure API calls.  | 
{: caption="Table 14. User management requestData fields" caption-side="top"} 



### Events for managing account usage reports
{: #at_events_analyze_4}

This section explains events that are generated when a user looks at the information that is provided through the  **Manage** &gt; **Billing and usage** &gt; **Usage** section, or request an export of the data.

You can get events with `reason.reasonCode = 404` that are generated when there is no usage data available for the request. The `severity` is set to normal.
{: note}

#### requestData fields
{: #at_events_analyze_4_reqdata}

The following table lists the fields that are available through the `requestData` field in the events with actions `billing.account-summary.read`, `billing.account-summary.download`, and `billing.account-instances-usage-report.download`:

| Field | Type | Description | Status | 
|-------|------|-------------|--------|
| `month` | String | Indicates the month that the user selects to view usage data. | Included always in the event |
{: caption="Table 15. Account usage summary requestData fields" caption-side="top"} 


The following table lists the fields that are available through the `requestData` field in the events with actions `billing.account-usage-report.read`:

| Field               | Type      | Description | Status |
|---------------------|-----------|-------------|--------|
| `month`             | String    | Indicates the month that the user selects to view usage data. |  Included always in the event |
| `usage_report_type` | String    | Indicates the type of report. </br>Valid values are `instances` and `rollup`.|  Included always in the event |
| `sub_account_id`    | String    | Indicates the sub-account ID. | Optional | 
| `resource_group`    | String    | Indicates the resource group. | Optional </br>Included if the user filters data by resource group. |
| `organization_id`   | String    | Indicates the organization ID. | Optional |
| `daily`             | Boolean   | Indicates the frequency of the report. | Optional |
{: caption="Table 16. Account usage requestData fields" caption-side="top"} 


The following table lists the fields that are available through the `requestData` field in the events with actions `billing.enterprise-usage-report.read` and `billing.enterprise-usage-report.download`:

| Field               | Type      | Description | Status |
|---------------------|-----------|-------------|--------|
| `month`             | String    | Indicates the month that the user selects to view usage data. |  Included always in the event |
| `children`          | Boolean   | Indicates whether the usage is aggregated at account level. | Included always in the event |
| `enterprise_id`     | String    | Indicates the ID of the enterprise. |  Included always in the event |
| `account_id`        | String    | Indicates the sub-account ID that is requested in the report. | Optional | 
| `account_group_id`  | String    | Indicates the account group when a user selects one. | Optional </br>Included if the user filters data by selecting 1 account group. |
{: caption="Table 17. Enterprise usage requestData fields" caption-side="top"} 


The following table lists the fields that are available through the `requestData` field in the events with actions `billing.enterprise-instances-usage-report.download`:

| Field               | Type      | Description | Status |
|---------------------|-----------|-------------|--------|
| `month`             | String    | Indicates the month that the user selects to view usage data. |  Included always in the event |
| `enterprise_id`     | String    | Indicates the ID of the enterprise. |  Included always in the event |
| `account_id`        | String    | Indicates the the sub-account IDs that is requested in the report. | Optional | 
| `account_group_id`  | String    | Indicates the account group when a user selects one. | Optional </br>Included if the user filters data by selecting 1 account group. |
{: caption="Table 18. Enterprise instances usage requestData fields" caption-side="top"} 



