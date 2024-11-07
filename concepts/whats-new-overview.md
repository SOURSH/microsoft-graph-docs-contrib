---
title: "What's new in Microsoft Graph"
description: "Find out what's new in Microsoft Graph APIs, SDKs, documentation, and other resources."
author: "lauragra"
ms.localizationpriority: high
---

# What's new in Microsoft Graph

Microsoft Graph provides a unified programmability model that you can use to access data in Microsoft 365, Windows, and Enterprise Mobility + Security. This article provides information about what's new in Microsoft Graph APIs, documentation, SDKs, and more.

For more detailed API-level updates, see the [Microsoft Graph API changelog](https://developer.microsoft.com/graph/changelog/).

For details about previous updates to Microsoft Graph, see [Microsoft Graph what's new history](whats-new-earlier.md).

> [!IMPORTANT]
> Features in _preview_ status are subject to change without notice, and might not be promoted to generally available (GA) status. Don't use preview features in production apps.

## November 2024: New and generally available

### Security | Identities

The Defender for Identity sensors management API enables you to create detailed reports on the sensors in your workspace, providing information such as server name, sensor version, type, state, and health status. It also allows you to manage sensor settings, including adding descriptions, enabling or disabling delayed updates, and specifying the domain controller the sensor connects to for querying Entra ID. For more information, see [sensor](/graph/api/resources/security-sensor).

## October 2024: New and generally available

### Backup storage

Updated the endpoints of the following methods:
- [List driveProtectionUnits](/graph/api/backuprestoreroot-list-driveprotectionunits)
- [List mailboxProtectionUnits](/graph/api/backuprestoreroot-list-mailboxprotectionunits)
- [List siteProtectionUnits](/graph/api/backuprestoreroot-list-siteprotectionunits)

### Change notifications

Enabled the `$notifyOnUserSpecificProperties` query parameter as a value of the **resource** property in the [subscription](/graph/api/resources/subscription?view=graph-rest-beta&preserve-view=true) resource. You can use the [notifyOnUserSpecificProperties](/graph/teams-changenotifications-chat#notification-payloads-for-user-specific-properties) parameter when you subscribe to [notifications in a particular chat](/graph/teams-changenotifications-chat#subscribe-to-changes-in-a-particular-chat).

### Identity and access | Directory management

- [Get](/graph/api/domain-get-rootdomain) the root domain of a subdomain.
- Added recommendations to use unified RBAC APIs in [unifiedRoleDefinition](/graph/api/resources/unifiedroledefinition) instead of [directoryRole](/graph/api/resources/directoryrole) and [directoryRoleTemplate](/graph/api/resources/directoryroletemplate).
- Use the **membershipRule** property on [administrativeUnit](/graph/api/resources/administrativeunit) to get or set the dynamic membership rule for an administrative unit.
- Use the **membershipRuleProcessingState** property on [administrativeUnit](/graph/api/resources/administrativeunit) to indicate whether the dynamic membership rule is actively processed.
- Use the **membershipType** property on [administrativeUnit](/graph/api/resources/administrativeunit) to get or set the membership type for an administrative unit.

### Security | eDiscovery

- Enabled the deletion of Exchange mailbox items in the [ediscoverySearch: purgeData](/graph/api/security-ediscoverysearch-purgedata) method.
- Deleted the `permanentlyDeleted` member from the **purgeType** enumeration in favor of the `permanentlyDelete` member.
- Export [results](/graph/api/security-ediscoverysearch-exportresult) and a [report](/graph/api/security-ediscoverysearch-exportreport) from an [ediscoverySearch](/graph/api/resources/security-ediscoverysearch).
- Legal holds are holds that are tied to an eDiscovery case. To learn more about a legal hold policy and its supported methods, see [ediscoveryHoldPolicy](/graph/api/resources/security-ediscoveryholdpolicy).

### Teamwork and communications | Apps

Use the **clientAppId** property on [teamsAppAuthorization](/graph/api/resources/teamsappauthorization) to get the registration ID of the Microsoft Entra app ID associated with an [app](/graph/api/resources/teamsapp) in the Microsoft Teams app catalog.

### Teamwork and communications | Calls and online meetings

Use the **isDeltaRosterEnabled** property on [incomingCallOptions](/graph/api/resources/incomingcalloptions) and [outgoingCallOptions](/graph/api/resources/outgoingcalloptions) to indicate whether delta roster is enabled for a call.

### Teamwork and communications | Messaging

- Updated the [chatMessage: delta](/graph/api/chatmessage-delta) method to use a new endpoint that gets the list of delta messages from all chats in which a user is a participant, including one-on-one chats, group chats, and meeting chats.
- Use the **reactionContentUrl** property on [chatMessageReaction](/graph/api/resources/chatmessagereaction) to represent the hosted content URL for a custom reaction in a [chatMessage](/graph/api/resources/chatmessage).
- Use the `<customemoji></customemoji>` tag on the **content** property of the [itemBody](/graph/api/resources/itembody) resource to represent custom emojis in the message body in a [chatMessage](/graph/api/resources/chatmessage).
- Use the **displayName** property on [chatMessageReaction](/graph/api/resources/chatmessagereaction) to represent the reaction name in a [chatMessage](/graph/api/resources/chatmessage).

## October 2024: New in preview only

### Backup storage

Added new endpoints for bulk addition of protection units into a protection policy:
- [Create siteProtectionUnitsBulkAdditionJob](/graph/api/siteprotectionunitsbulkadditionjobs-post?view=graph-rest-beta&preserve-view=true)
- [List siteProtectionUnitsBulkAdditionJobs](/graph/api/sharepointprotectionpolicy-list-siteprotectionunitsbulkadditionjobs?view=graph-rest-beta&preserve-view=true)
- [Get siteProtectionUnitsBulkAdditionJob](/graph/api/siteprotectionunitsbulkadditionjobs-get?view=graph-rest-beta&preserve-view=true)

- [Create mailboxProtectionUnitsBulkAdditionJob](/graph/api/mailboxprotectionunitsbulkadditionjobs-post?view=graph-rest-beta&preserve-view=true)
- [List mailboxProtectionUnitsBulkAdditionJobs](/graph/api/onedriveforbusinessprotectionpolicy-list-driveprotectionunitsbulkadditionjobs?view=graph-rest-beta&preserve-view=true)
- [Get mailboxProtectionUnitsBulkAdditionJob](/graph/api/mailboxprotectionunitsbulkadditionjobs-get?view=graph-rest-beta&preserve-view=true) 

- [Create driveProtectionUnitsBulkAdditionJob](/graph/api/driveprotectionunitsbulkadditionjobs-post?view=graph-rest-beta&preserve-view=true)
- [List driveProtectionUnitsBulkAdditionJobs](/graph/api/exchangeprotectionpolicy-list-mailboxprotectionunitsbulkadditionjobs?view=graph-rest-beta&preserve-view=true)
- [Get driveProtectionUnitsBulkAdditionJob](/graph/api/driveprotectionunitsbulkadditionjobs-get?view=graph-rest-beta&preserve-view=true)

Updated the endpoints of the following methods:
- [List driveProtectionUnits](/graph/api/backuprestoreroot-list-driveprotectionunits?view=graph-rest-beta&preserve-view=true)
- [List mailboxProtectionUnits](/graph/api/backuprestoreroot-list-mailboxprotectionunits?view=graph-rest-beta&preserve-view=true)
- [List siteProtectionUnits](/graph/api/backuprestoreroot-list-siteprotectionunits?view=graph-rest-beta&preserve-view=true)

### Device and app management | Cloud licensing

- Use the new cloud licensing [usageRight](/graph/api/resources/cloudlicensing-usageright?view=graph-rest-beta&preserve-view=true) entity that is designed for client and workload license checks, with relationships structured to flow from the user or group to the **usageRight**. This new entity supports the following operations:
  -  [List usage rights for a group](/graph/api/cloudlicensing-groupcloudlicensing-list-usagerights?view=graph-rest-beta&preserve-view=true)
  -  [List usage rights for a user](/graph/api/cloudlicensing-usercloudlicensing-list-usagerights?view=graph-rest-beta&preserve-view=true)
  -  [Get usage rights for a group or user](/graph/api/cloudlicensing-usageright-get?view=graph-rest-beta&preserve-view=true)
- Use the **cloudLicensing** property on a [group](/graph/api/resources/group?view=graph-rest-beta&preserve-view=true) or [user](/graph/api/resources/user?view=graph-rest-beta&preserve-view=true) to get their relationships with cloud licensing resources.

### Device and app management | Cloud PC

- Enabled the `$select` query parameter for the [cloudPC: getProvisionedCloudPCs](/graph/api/cloudpc-getprovisionedcloudpcs?view=graph-rest-beta&preserve-view=true) method.
- Use the **notificationSetting** property on [cloudPcUserSetting](/graph/api/resources/cloudpcnotificationsetting?view=graph-rest-beta&preserve-view=true) to define the Cloud PC notification prompts for a Cloud PC user.
- Enabled the `cloudPcFrontlineBufferUsageScenario` member in the **alertRuleTemplate** enumeration.
- Enabled the `frontlineBufferUsageDuration` and `frontlineBufferUsageThreshold` members in the **ruleCondition** enumeration.

### Identity and access | Directory management

Get or update the [uxSetting](/graph/api/resources/uxsetting?view=graph-rest-beta&preserve-view=true) that restricts access to Microsoft Entra admin center to only administrators.

### Identity and access | Identity and sign-in

Enabled `suspiciousAPITraffic` as a supported value for the **riskEventType** property in the [servicePrincipalRiskDetection](/graph/api/resources/serviceprincipalriskdetection?view=graph-rest-beta&preserve-view=true) resource. You can retrieve this value when you use either the [List servicePrincipalRiskDetections](/graph/api/identityprotectionroot-list-serviceprincipalriskdetections?view=graph-rest-beta&preserve-view=true) or [Get servicePrincipalRiskDetection](/graph/api/serviceprincipalriskdetection-get?view=graph-rest-beta&preserve-view=true) APIs.

### Reports | Identity and access reports

The Microsoft Entra Health monitoring alerts APIs enable you to detect anomalous usage patterns in business-critical identity scenarios for your tenant and receive alert notifications. Use the operations of the [alert](/graph/api/resources/healthmonitoring-alert?view=graph-rest-beta&preserve-view=true) and [alertConfiguration](/graph/api/resources/healthmonitoring-alertconfiguration?view=graph-rest-beta&preserve-view=true) resources to retrieve and update alerts and alert configurations. For details, see the [related changelog section](https://developer.microsoft.com/en-us/graph/changelog/?search=277da918-3e81-499f-8803-2986a2c73123).

### Security | eDiscovery

- Enabled the deletion of Exchange mailbox items in the [ediscoverySearch: purgeData](/graph/api/security-ediscoverysearch-purgedata?view=graph-rest-beta&preserve-view=true) method.
- Deleted the `permanentlyDeleted` member from the **purgeType** enumeration in favor of the `permanentlyDelete` member.

### Sites and lists

Updated the endpoints of the following methods:
- [Get](/graph/api/pagetemplate-get?view=graph-rest-beta&preserve-view=true)
- [Update](/graph/api/pagetemplate-update?view=graph-rest-beta&preserve-view=true)
- [Delete](/graph/api/pagetemplate-delete?view=graph-rest-beta&preserve-view=true)

### Teamwork and communications | Calls and online meetings

- Use the **externalRegistrationInformation** property on [virtualEventRegistration](/graph/api/resources/virtualeventregistration?view=graph-rest-betaa&preserve-view=true) to get or set the external information for a virtual event registration.
- Use the following new methods for virtual events that are of the [virtualEventTownhall](/graph/api/resources/virtualeventtownhall?view=graph-rest-beta&preserve-view=true) type:
  - [List](/graph/api/virtualeventsroot-list-townhalls?view=graph-rest-beta&preserve-view=true) all virtual event town halls created in a tenant.
  - [Get](/graph/api/virtualeventtownhall-getbyuseridandrole?view=graph-rest-beta&preserve-view=true) the virtual event town halls where a specified user is an organizer or coorganizer.
  - [Get](/graph/api/virtualeventtownhall-getbyuserrole?view=graph-rest-beta&preserve-view=true) the virtual event town halls where the signed-in user is an organizer or coorganizer.

### Teamwork and communications | Messaging

- Updated the [chatMessage: delta](/graph/api/chatmessage-delta?view=graph-rest-beta&preserve-view=true) method to use a new endpoint that gets the list of delta messages from all chats in which a user is a participant, including one-on-one chats, group chats, and meeting chats.
- [Get](/graph/api/chatmessage-get?view=graph-rest-beta&preserve-view=true#example-6-get-a-chat-message-with-a-forwarded-message) a chat message that has a forwarded message as an attachment.
- [Remove multiple members](/graph/api/conversationmember-remove?view=graph-rest-beta&preserve-view=true) from a [team](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true) in a single request.

### Users

Changed the following on-premises synced properties of the [user](/graph/api/resources/user?view=graph-rest-beta&preserve-view=true) resource type that were read-only in Microsoft Graph to be updatable via Microsoft Graph: 
- onPremisesDistinguishedName
- onPremisesDomainName
- onPremisesSamAccountName
- onPremisesSecurityIdentifier
- onPremisesUserPrincipalName

## Contribute to Microsoft Graph

Are there scenarios you'd like Microsoft Graph to support?

- Suggest and vote for new features by using the [Microsoft Graph Feedback Portal](https://aka.ms/graphfeedback). Some new features originate as popular requests from the developer community. The Microsoft Graph team regularly evaluates customer needs and releases new features to the beta (`https://graph.microsoft.com/beta`) and v1.0 (`https://graph.microsoft.com/v1.0`) endpoints.

- [Join](https://aka.ms/m365-dev-call) the weekly Microsoft 365 platform community call and become an active member of the Microsoft Graph community. To discover the full calendar of developer calls, visit the [Microsoft 365 and Power Platform community page](https://aka.ms/community/calls).

- [Join](https://ux.microsoft.com/Panel/M365Devs?utm_source=graphDocs) our research panel to provide your input on our developer experiences.

## Related content
- [Microsoft Graph developer blog](https://devblogs.microsoft.com/microsoft365dev/category/microsoft-graph/).
- [Microsoft Graph API changelog](https://developer.microsoft.com/graph/changelog/).
- [Microsoft Graph what's new history](whats-new-earlier.md).
