---
external_help_file: Microsoft.Azure.Commands.PolicyInsights.dll-Help.xml
Module_Name: AzureRM.PolicyInsights
online_version: https://docs.microsoft.com/en-us/powershell/module/azurerm.policyinsights/get-azurermpolicystate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/PolicyInsights/Commands.PolicyInsights/help/Get-AzureRmPolicyState.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/PolicyInsights/Commands.PolicyInsights/help/Get-AzureRmPolicyState.md
---

# Get-AzureRmPolicyState

## SYNOPSIS
Gets policy compliance states for resources.

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzureRmPolicyState [-All] [-SubscriptionId <String>] [-Top <Int32>] [-OrderBy <String>] [-Select <String>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ManagementGroupScope
```
Get-AzureRmPolicyState [-All] -ManagementGroupName <String> [-Top <Int32>] [-OrderBy <String>]
 [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupScope
```
Get-AzureRmPolicyState [-All] [-SubscriptionId <String>] -ResourceGroupName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceScope
```
Get-AzureRmPolicyState [-All] -ResourceId <String> [-Top <Int32>] [-OrderBy <String>] [-Select <String>]
 [-From <DateTime>] [-To <DateTime>] [-Filter <String>] [-Apply <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicySetDefinitionScope
```
Get-AzureRmPolicyState [-All] [-SubscriptionId <String>] -PolicySetDefinitionName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyDefinitionScope
```
Get-AzureRmPolicyState [-All] [-SubscriptionId <String>] -PolicyDefinitionName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SubscriptionLevelPolicyAssignmentScope
```
Get-AzureRmPolicyState [-All] [-SubscriptionId <String>] -PolicyAssignmentName <String> [-Top <Int32>]
 [-OrderBy <String>] [-Select <String>] [-From <DateTime>] [-To <DateTime>] [-Filter <String>]
 [-Apply <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupLevelPolicyAssignmentScope
```
Get-AzureRmPolicyState [-All] [-SubscriptionId <String>] -ResourceGroupName <String>
 -PolicyAssignmentName <String> [-Top <Int32>] [-OrderBy <String>] [-Select <String>] [-From <DateTime>]
 [-To <DateTime>] [-Filter <String>] [-Apply <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets policy compliance states for resources. Policy state records can be queried at various scopes. Based on the time interval specified (defaults to last day), either latest policy states or all policy state transitions can be queried. Results can be filtered, grouped, and group aggregations can be computed.

## EXAMPLES

### Example 1: Get latest policy states in current subscription scope
```powershell
PS C:\> Get-AzureRmPolicyState
```

Gets latest policy state records generated in the last day for all resources within the subscription in current session context.

### Example 2: Get latest policy states in the specified subscription scope
```powershell
PS C:\> Get-AzureRmPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5"
```

Gets latest policy state records generated in the last day for all resources within the specified subscription.

### Example 3: Get all policy states in current subscription scope
```powershell
PS C:\> Get-AzureRmPolicyState -All
```

Gets all historical policy state records (including latest) generated in the last day for all resources within the subscription in current session context.

### Example 4: Get latest policy states in management group scope
```powershell
PS C:\> Get-AzureRmPolicyState -ManagementGroupName "myManagementGroup"
```

Gets latest policy state records generated in the last day for all resources within the specified management group.

### Example 5: Get latest policy states in resource group scope in current subscription
```powershell
PS C:\> Get-AzureRmPolicyState -ResourceGroupName "myResourceGroup"
```

Gets latest policy state records generated in the last day for all resources within the specified resource group (in the subscription in current session context).

### Example 6: Get latest policy states in resource group scope in the specified subscription
```powershell
PS C:\> Get-AzureRmPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -ResourceGroupName "myResourceGroup"
```

Gets latest policy state records generated in the last day for all resources within the specified resource group (in the specified subscription).

### Example 7: Get latest policy states for a resource
```powershell
PS C:\> Get-AzureRmPolicyState -ResourceId "/subscriptions/fff10b27-fff3-fff5-fff8-fffbe01e86a5/resourceGroups/myResourceGroup/providers/Microsoft.EventHub/namespaces/myns1/eventhubs/eh1/consumergroups/cg1"
```

Gets latest policy state records generated in the last day for the specified resource.

### Example 8: Get latest policy states for a policy set definition in current subscription
```powershell
PS C:\> Get-AzureRmPolicyState -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Gets latest policy state records generated in the last day for all resources (within the tenant in current session context) effected by the specified policy set definition (that exists in the subscription in current session context).

### Example 9: Get latest policy states for a policy set definition in the specified subscription
```powershell
PS C:\> Get-AzureRmPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicySetDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Gets latest policy state records generated in the last day for all resources (within the tenant in current session context) effected by the specified policy set definition (that exists in the specified subscription).

### Example 10: Get latest policy states for a policy definition in current subscription
```powershell
PS C:\> Get-AzureRmPolicyState -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Gets latest policy state records generated in the last day for all resources (within the tenant in current session context) effected by the specified policy definition (that exists in the subscription in current session context).

### Example 11: Get latest policy states for a policy definition in the specified subscription
```powershell
PS C:\> Get-AzureRmPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyDefinitionName "fff58873-fff8-fff5-fffc-fffbe7c9d697"
```

Gets latest policy state records generated in the last day for all resources (within the tenant in current session context) effected by the specified policy definition (that exists in the specified subscription).

### Example 12: Get latest policy states for a policy assignment in current subscription
```powershell
PS C:\> Get-AzureRmPolicyState -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Gets latest policy state records generated in the last day for all resources (within the tenant in current session context) effected by the specified policy assignment (that exists in the subscription in current session context).

### Example 13: Get latest policy states for a policy assignment in the specified subscription
```powershell
PS C:\> Get-AzureRmPolicyState -SubscriptionId "fff10b27-fff3-fff5-fff8-fffbe01e86a5" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1"
```

Gets latest policy state records generated in the last day for all resources (within the tenant in current session context) effected by the specified policy assignment (that exists in the specified subscription).

### Example 14: Get latest policy states for a policy assignment in the specified resource group in the current subscription
```powershell
PS C:\> Get-AzureRmPolicyState -ResourceGroupName "myResourceGroup" -PolicyAssignmentName "ddd8ef92e3714a5ea3d208c1" 
```

Gets latest policy state records generated in the last day for all resources (within the tenant in current session context) effected by the specified policy assignment (that exists in the resource group in the subscription in current session context).

### Example 15: Get latest policy states in current subscription scope, with OrderBy, Top and Select query options
```powershell
PS C:\> Get-AzureRmPolicyState -OrderBy "Timestamp desc, PolicyAssignmentName asc" -Top 5 -Select "Timestamp, ResourceId, PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionId, IsCompliant"
```

Gets latest policy state records generated in the last day for all resources within the subscription in current session context. 
The command orders the results by timestamp and policy assignment name properties, and takes only top 5 of those listed in that order.
It also selects to list only a subset of the columns for each record.

### Example 16: Get latest policy states in current subscription scope, with From and To query options
```powershell
PS C:\> Get-AzureRmPolicyState -From "2018-03-08 00:00:00Z" -To "2018-03-15 00:00:00Z"
```

Gets latest policy state records generated within the date range specified for all resources within the subscription in current session context.

### Example 17: Get latest policy states in current subscription scope, with Filter query option
```powershell
PS C:\> Get-AzureRmPolicyState -Filter "(PolicyDefinitionAction eq 'deny' or PolicyDefinitionAction eq 'audit') and IsCompliant eq false and ResourceLocation ne 'eastus'"
```

Gets latest policy state records generated in the last day for all resources within the subscription in current session context.
The command limits the results returned by filtering based on policy definition action (includes deny or audit actions), compliance status (includes only non-compliant status) and resource location (excludes eastus location).

### Example 18: Get latest policy states in current subscription scope, with Apply specifying row count aggregation
```powershell
PS C:\> Get-AzureRmPolicyState -Apply "aggregate(`$count as NumberOfRecords)"
```

Gets the number of latest policy state records generated in the last day for all resources within the subscription in current session context.
The command returns the count of the policy state records only, which is returned inside AdditionalProperties property.

### Example 19: Get latest policy states in current subscription scope, with Apply specifying grouping with aggregation
```powershell
PS C:\> Get-AzureRmPolicyState -Filter "IsCompliant eq false" -Apply "groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId), aggregate(`$count as NumStates))" -OrderBy "NumStates desc" -Top 5
```

Gets latest policy state records generated in the last day for all resources within the subscription in current session context. 
The command limits the results returned by filtering based on compliance status (includes only non-compliant status).
It groups the results based on policy assignment, policy set definition, and policy definition, and computes the number of records in each group, which is returned inside AdditionalProperties property.
It orders the results by the count aggregation in descending order, and takes only top 5 of those listed in that order.

### Example 20: Get latest policy states in current subscription scope, with Apply specifying grouping without aggregation
```powershell
PS C:\> Get-AzureRmPolicyState -Filter "IsCompliant eq false" -Apply "groupby((ResourceId))"
```

Gets latest policy state records generated in the last day for all resources within the subscription in current session context. 
The command limits the results returned by filtering based on compliance status (includes only non-compliant status).
It groups the results based on resource id.
This generates the list of all resources within the subscription that are non-compliant for at least one policy.

### Example 21: Get latest policy states in current subscription scope, with Apply specifying multiple groupings
```powershell
PS C:\> Get-AzureRmPolicyState -Filter "IsCompliant eq false" -Apply "groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId, ResourceId))/groupby((PolicyAssignmentId, PolicySetDefinitionId, PolicyDefinitionReferenceId, PolicyDefinitionId), aggregate(`$count as NumNonCompliantResources))" -OrderBy "NumNonCompliantResources desc" -Top 5
```

Gets latest policy state records generated in the last day for all resources within the subscription in current session context. 
The command limits the results returned by filtering based on compliance status (includes only non-compliant status).
It groups the results first based on policy assignment, policy set definition, policy definition, and resource id. 
Then, it further groups the results of this grouping with the same properties except for resource id, and computes the number of records in each of these groups, which is returned inside AdditionalProperties property.
It orders the results by the count aggregation in descending order, and takes only top 5 of those listed in that order.
This generates the top 5 policies with the most number of non-compliant resources.

## PARAMETERS

### -All
Within the specified time interval, get all policy states instead of the latest only.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Apply
Apply expression for aggregations using OData notation.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Filter expression using OData notation.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -From
ISO 8601 formatted timestamp specifying the start time of the interval to query.
When not specified, defaults to 'To' parameter value minus 1 day.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementGroupName
Management group name.

```yaml
Type: String
Parameter Sets: ManagementGroupScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OrderBy
Ordering expression using OData notation.
One or more comma-separated column names with an optional 'desc' (the default) or 'asc'.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyAssignmentName
Policy assignment name.

```yaml
Type: String
Parameter Sets: SubscriptionLevelPolicyAssignmentScope, ResourceGroupLevelPolicyAssignmentScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyDefinitionName
Policy definition name.

```yaml
Type: String
Parameter Sets: PolicyDefinitionScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicySetDefinitionName
Policy set definition name.

```yaml
Type: String
Parameter Sets: PolicySetDefinitionScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Resource group name.

```yaml
Type: String
Parameter Sets: ResourceGroupScope, ResourceGroupLevelPolicyAssignmentScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Resource ID.

```yaml
Type: String
Parameter Sets: ResourceScope
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Select
Select expression using OData notation.
One or more comma-separated column names.
Limits the columns on each record to just those requested.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Subscription ID.

```yaml
Type: String
Parameter Sets: SubscriptionScope, ResourceGroupScope, PolicySetDefinitionScope, PolicyDefinitionScope, SubscriptionLevelPolicyAssignmentScope, ResourceGroupLevelPolicyAssignmentScope
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -To
ISO 8601 formatted timestamp specifying the start time of the interval to query.
When not specified, defaults to 'To' parameter value minus 1 day.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Maximum number of records to return.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.PolicyInsights.Models.PolicyState, Microsoft.Azure.Commands.PolicyInsights, Version=0.9.0.0, Culture=neutral, PublicKeyToken=null]]

## NOTES

## RELATED LINKS

[Get-AzureRmPolicyStateSummary](./Get-AzureRmPolicyStateSummary.md)
