# Activity details for Overall API call volume<a name="profile-panel-drilldown-overall-api-volume"></a>

The activity details for **Overall API call volume** show the API calls that were issued during a selected time range\.

To display the activity details for a single time interval, choose the time interval on the chart\.

To display the activity details for the current scope time, choose **Display details for scope time**\.

Note that Detective began to store and display the service name for API calls as of July 14, 2021\. That date is highlighted on the profile panel timeline\. For activity that occurs before that date, the service name is **Unknown service**\.

## Content of the activity details \(users, roles, accounts, role sessions, EC2 instances\)<a name="drilldown-api-volume-content"></a>

For users, roles, accounts, and role sessions, the activity details contain the following information:
+ Each tab provides information about the set of API calls that were issued during the selected time range\. The API calls are grouped by the services that called them\. If Detective cannot determine the service that issued a call, the call is listed under **Unknown service**\.
+ For each entry, the activity details show the number of successful and failed calls\. The **Observed IP addresses** tab also shows the location of each IP address\.
+ Each entry also shows information about who made the calls\. For accounts, the activity details identify the users or roles\. For roles, the activity details identify the role sessions\. For users and role sessions, the activity details identify the access key identifiers \(AKIDs\)\.

  Note that as of July 14, 2021, for account profiles, the activity details show users or roles instead of AKIDs\. For role profiles, the activity details show role sessions instead of AKIDs\. For activity that occurs before July 14, 2021, the caller is listed as **Unknown resource**\.

The activity details contain the following tabs:

**Observed IP addresses**  
Initially displays the list of IP addresses used to issue API calls\.  
You can expand each IP address to display the list of API calls that were issued from that IP address\. The API calls are grouped by the services that called them\. If Detective cannot determine the service that issued a call, the call is listed under **Unknown service**\.  
You can then expand each API call to display the list of callers from that IP address\. Depending on the profile, the caller might be a user, role, role session, or AKID\.  

![\[View of the Observed IP addresses tab of the Overall API call volume panel, with an entry expanded to show the hierarchy of IP address, API calls, and AKIDs. API calls are grouped by service.\]](http://docs.aws.amazon.com/detective/latest/userguide/images/screen_profile_panel_drilldown_api_ipaddress.png)

**API method by service**  
Initially displays the list of API calls that were issued\. The API calls are grouped by the services that issued the calls\. If Detective cannot determine the service that issued a call, the call is listed under **Unknown service**\.  
You can expand each API method to display the list of IP addresses from which the calls were issued\.  
You can then expand each IP address to display the list of AKIDs that issued that API call from that IP address\.  

![\[View of the API method by service tab of the Overall API call volume panel, with an entry expanded to show the hierarchy of API calls, IP addresses, and AKIDs. API calls are grouped by service\]](http://docs.aws.amazon.com/detective/latest/userguide/images/screen_profile_panel_drilldown_api_apimethods.png)

**Resource or Access Key ID**  
Initially displays the list of users, roles, role sessions, or AKIDs that were used to issue API calls\.  
You can expand each caller to display the list of IP addresses from which the caller issued API calls\.  
You can then expand each IP address to display the list of API calls that were issued from that IP address by that caller\. The API calls are grouped by the services that issued the calls\. If Detective cannot determine the service that issued a call, the call is listed under** Unknown service**\.  

![\[View of the Resource tab of the Overall API call volume panel, with an entry expanded to show the hierarchy of AKIDs, IP addresses, and API calls grouped by service.\]](http://docs.aws.amazon.com/detective/latest/userguide/images/screen_profile_panel_drilldown_api_resource.png)

## Content of the activity details \(IP addresses\)<a name="drilldown-api-volume-content-ip"></a>

For IP addresses, the activity details contain the following information:
+ Each tab provides information about the set of API calls that were issued during the selected time range\. The API calls are grouped by the services that issued the calls\. If Detective cannot determine the service that issued a call, the call is listed under **Unknown service**\.
+ For each entry, the activity details show the number of successful and failed calls\.

The activity details contain the following tabs:

**Resource**  
Initially displays the list of resources that issued API calls from the IP address\.  
For each resource, the list includes the resource name, the type, and the AWS account\.  
You can expand each resource to display the list of API calls that the resource issued from the IP address\. The API calls are grouped by the services that issued the calls\. If Detective cannot determine the service that issued a call, the call is listed under **Unknown service**\.  

![\[View of the Resource tab of the activity details on the Overall API call volume profile panel for an IP address\]](http://docs.aws.amazon.com/detective/latest/userguide/images/screen_profile_panel_drilldown_api_ip_resource.png)

**API method by service**  
Initially displays the list of API calls that were issued\. The API calls are grouped by the services that issued the calls\. If Detective cannot determine the service that issued a call, the call is listed under **Unknown service**\.  
You can expand each API call to display the list of resources that issued the API call from the IP address during the selected time period\.  

![\[View of the API method by service tab of the activity details of the Overall API call volume profile panel for an IP address\]](http://docs.aws.amazon.com/detective/latest/userguide/images/screen_profile_panel_drilldown_api_ip_apimethods.png)

## Sorting the activity details<a name="drilldown-api-volume-sort"></a>

You can sort the activity details by any of the list columns\.

When you sort using the first column, only the top\-level list is sorted\. The lower\-level lists are always sorted by the count of successful API calls\.

## Filtering the activity details<a name="drilldown-api-volume-filter"></a>

You can use the filtering options to focus on specific subsets or aspects of the activity represented in the activity details\.

On all of the tabs, you can filter the list by any of the values in the first column\.

**To add a filter**

1. Choose the filter box\.

1. From **Properties**, choose the property to use for the filtering\.

1. Provide the value to use for the filtering\. The filter supports partial values\. For example, when you filter by API method, if you filter by **Instance**, the results include any API operation that has `Instance` in its name\. So both `ListInstanceAssociations` and `UpdateInstanceInformation` would match\.

   For service names, API methods, and IP addresses, you can either specify a value or choose a built\-in filter\.

   For **Common API substrings**, choose the substring that represents the type of operation, such as `List`, `Create`, or `Delete`\. Each API method name starts with the operation type\.

   For **CIDR patterns**, you can choose to include only public IP addresses, private IP addresses, or IP addresses that match a specific CIDR pattern\.

1. If you have multiple filters, choose a Boolean option to set how those filters are connected\.  
![\[List of available connectors between individual filters for the activity details filter.\]](http://docs.aws.amazon.com/detective/latest/userguide/images/screen_profile_panel_drilldown_filterconnectors.png)

1. To remove a filter, choose the **x** icon in the top\-right corner\.

1. To clear all of the filters, choose **Clear filter**\.

## Selecting the time range for the activity details<a name="drilldown-api-volume-time-range"></a>

 When you first display the activity details, the time range is either the scope time or a selected time interval\. You can change the time range for the activity details\.

**To change the time range for the activity details**

1. Choose **Edit**\.

1. On **Edit time window**, choose the start and end time to use\.

   To set the time window to the default scope time for the profile, choose **Set to default scope time**\.

1. Choose **Update time window**\.

The time range for the activity details is highlighted on the profile panel charts\.

![\[Highlighted time window for the Overall API call volume profile panel\]](http://docs.aws.amazon.com/detective/latest/userguide/images/screen_profile_panel_drilldown_api_timehighlight.png)