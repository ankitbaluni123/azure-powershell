---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
ms.assetid: 6A08AF7C-1E18-40A1-B21E-12F94823D304
online version: https://learn.microsoft.com/powershell/module/az.operationalinsights/new-azoperationalinsightscustomlogdatasource
schema: 2.0.0
---

# New-AzOperationalInsightsCustomLogDataSource

## SYNOPSIS
Defines a custom log collection policy.

## SYNTAX

### ByWorkspaceName (Default)
```
New-AzOperationalInsightsCustomLogDataSource [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-Name] <String> [-CustomLogRawJson] <String> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByWorkspaceObject
```
New-AzOperationalInsightsCustomLogDataSource [-Workspace] <PSWorkspace> [-Name] <String>
 [-CustomLogRawJson] <String> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzOperationalInsightsCustomLogDataSource** cmdlet defines a custom log collection policy.

## EXAMPLES

### Example 1: Defines a custom log collection policy 

```powershell
$customLogRawJson = '{"customLogName":"Validation_CL","description":"test","inputs":[{"location":{"fileSystemLocations":{"linuxFileTypeLogPaths":null,"windowsFileTypeLogPaths":["C:\\e2e\\Evan\\ArubaSECURITY\\*.log"]}},"recordDelimiter":{"regexDelimiter":{"pattern":"\\n","matchIndex":0}}}],"extractions":[{"extractionName":"TimeGenerated","extractionType":"DateTime","extractionProperties":{"dateTimeExtraction":{"regex":"((\\d{2})|(\\d{4}))-([0-1]\\d)-(([0-3]\\d)|(\\d))\\s((\\d)|([0-1]\\d)|(2[0-4])):[0-5][0-9]:[0-5][0-9]","joinStringRegex":null}}}]}'
New-AzOperationalInsightsCustomLogDataSource -ResourceGroupName rg-name -WorkspaceName workspace-name -CustomLogRawJson $customLogRawJson -Name "MyCustomLog"
```

```output
Name              : MyCustomLog
ResourceGroupName : rg-name
WorkspaceName     : workspace-name
ResourceId        : /subscriptions/sub-id/resourceGroups/rg-name/providers/Microsoft.OperationalInsights/workspaces/workspace-name/datasources/MyCustomLog
Kind              : CustomLog
Properties        : {"customLogName":"Validation_CL","description":"test","extractions":[{"extractionName":"TimeGenerated","extractionProperties":{"dateTimeExtraction":{"joinStringRegex":null,"regex":[{"m
                    atchIndex":0,"numberdGroup":null,"pattern":"((\\d{2})|(\\d{4}))-([0-1]\\d)-(([0-3]\\d)|(\\d))\\s((\\d)|([0-1]\\d)|(2[0-4])):[0-5][0-9]:[0-5][0-9]"}],"formatString":null}},"extractionTy
                    pe":"DateTime"}],"inputs":[{"location":{"fileSystemLocations":{"linuxFileTypeLogPaths":null,"windowsFileTypeLogPaths":["C:\\e2e\\Evan\\ArubaSECURITY\\*.log"]}},"recordDelimiter":{"rege
                    xDelimiter":{"matchIndex":0,"numberdGroup":null,"pattern":"\\n"}}}]}
```

The response received after defining a custom log collection policy 

## PARAMETERS

### -CustomLogRawJson
Specifies the custom collection policy as a raw JavaScript Object Notation (JSON) string.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the data source.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group that contains computers.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Workspace
Specifies a workspace in which this cmdlet operates.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter Sets: ByWorkspaceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkspaceName
Specifies the name of a workspace in which this cmdlet operates.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataSource

## NOTES

## RELATED LINKS

[Disable-AzOperationalInsightsLinuxCustomLogCollection](./Disable-AzOperationalInsightsLinuxCustomLogCollection.md)

[Enable-AzOperationalInsightsLinuxCustomLogCollection](./Enable-AzOperationalInsightsLinuxCustomLogCollection.md)


