﻿
# Add-Applibtaskmetadata
Adds metadata on the given Task.
## Syntax
```
Add-AppLibTaskMetadata [-TaskId] <Guid> -Map <PSObject> [-LoggingId <Guid>] [-BearerToken <String>] [-AdminAddress <String>] [<CommonParameters>]

Add-AppLibTaskMetadata [-TaskId] <Guid> -Name <String> -Value <String> [-LoggingId <Guid>] [-BearerToken <String>] [-AdminAddress <String>] [<CommonParameters>]

Add-AppLibTaskMetadata [-InputObject] <Task[]> -Name <String> -Value <String> [-LoggingId <Guid>] [-BearerToken <String>] [-AdminAddress <String>] [<CommonParameters>]

Add-AppLibTaskMetadata [-InputObject] <Task[]> -Map <PSObject> [-LoggingId <Guid>] [-BearerToken <String>] [-AdminAddress <String>] [<CommonParameters>]
```
## Detailed Description
Use this cmdlet to store additional custom data against given Task objects. This cmdlet does not overwrite existing metadata on an object - use the Set-AppLibTaskMetadata cmdlet instead.


## Related Commands

* [Set-AppLibTaskMetadata](./Set-AppLibTaskMetadata/)
* [Remove-AppLibTaskMetadata](./Remove-AppLibTaskMetadata/)
* [Get-AppLibTask](./Get-AppLibTask/)
* [Stop-AppLibTask](./Stop-AppLibTask/)
* [Remove-AppLibTask](./Remove-AppLibTask/)
* [Switch-AppLibTask](./Switch-AppLibTask/)
## Parameters
| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| TaskId | Id of the Task | true | true (ByValue, ByPropertyName) |  |
| InputObject | Objects to which the metadata is to be added. | true | true (ByValue) |  |
| Map | Specifies a dictionary of (name, value)-pairs for the properties. This can be either a hashtable (created with @{"name1" = "val1"; "name2" = "val2"}) or a string dictionary (created with new-object "System.Collections.Generic.Dictionary\[String,String\]"). | true | true (ByValue) |  |
| Name | Specifies the property name of the metadata to be added. The property must be unique for the Task specified. The property cannot contain any of the following characters \\/;:#.\*?=&lt;&gt;|\[\]()"' | true | false |  |
| Value | Specifies the value for the property. | true | false |  |
| LoggingId | Specifies the identifier of the high-level operation this cmdlet call forms a part of. Citrix Studio and Director typically create high-level operations. PowerShell scripts can also wrap a series of cmdlet calls in a high-level operation by way of the Start-LogHighLevelOperation and Stop-LogHighLevelOperation cmdlets. | false | false |  |
| BearerToken | Specifies the bearer token assigned to the calling user | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller the PowerShell snap-in will connect to. You can provide this as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value becomes the default. |

## Input Type

### 

## Return Values

### Citrix.Applibrary.Sdk.Metadata<br>   Add-Applibtaskmetadata Returns An Array Of Objects Containing The New Definition Of The Metadata.<br>    Property &lt;String&gt;<br>        Specifies The Name Of The Property.<br>    Value &lt;String&gt;<br>        Specifies The Value For The Property.

## Notes
If the command fails, the following errors can result.<br>    Error Codes<br>    -----------<br>    InvalidParameterCombination<br>        The cmdlet parameters are inconsistent.<br>    UnknownObject<br>        One of the specified objects was not found.<br>    DuplicateObject<br>        One of the specified metadata already exists.<br>    DatabaseError<br>        An error occurred in the service while attempting a database operation.<br>    DatabaseNotConfigured<br>        The operation could not be completed because the database for the service is not configured.<br>    DataStoreException<br>        An error occurred in the service while attempting a database operation - communication with the database failed for various reasons.<br>    PermissionDenied<br>        You do not have permission to execute this command.<br>    AuthorizationError<br>        There was a problem communicating with the Citrix Delegated Administration Service.<br>    ConfigurationLoggingError<br>        The operation could not be performed because of a configuration logging error.<br>    CommunicationError<br>        There was a problem communicating with the remote service.<br>    ExceptionThrown<br>        An unexpected error occurred.  For more details, see the Windows event logs on the controller or the XenDesktop logs.
## Examples

### Example 1
```
c:\PS>Add-AppLibTaskMetadata -TaskId 4CECC26E-48E1-423F-A1F0-2A06DDD0805C -Name property -Value value

          Property                                  Value

          --------                                  -----

          property                                  value
```
#### Description
Add metadata with a name of 'property' and a value of 'value' to the Task with the identifier '4CECC26E-48E1-423F-A1F0-2A06DDD0805C'.
