## Mapping

|Source Table (API File)	|Source Fields	|Target Field	|Include	|Concat	|Data Type	|Null	|Default Value	|Model Field	|Type of Field|
| -------------- | --------------- | ----------------- | ------- | ------ | ---------- | ---- | ------------- | -------------- | --------------------- |
|	|IDENTITY (1,1)	|WorkItemHierarchyID	|1	|0	|INT	|0	|-1	|WorkItemHierarchyID	|pk|
|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/list?view=azure-devops-rest-6.0&tabs=HTTP	|fields{System.WorkItemType}	|Feature	|1	|0	|VARCHAR(50)	|1	|Unknown	|Feature	|ref|
|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/list?view=azure-devops-rest-6.0&tabs=HTTP	|fields{System.WorkItemType}	|Epic	|1	|0	|VARCHAR(50)	|1	|Unknown	|Epic	|ref|
|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/list?view=azure-devops-rest-6.0&tabs=HTTP	|relations{url, name}	|EpicType	|1	|0	|INT	|0	|Unknown	|EpicType	|ref|



## Keys, Indexes, Partitions
| Name            | Type                           | On         | Including |
| --------------- | ------------------------------ | ---------- | --------- |
| PK_WorkItemHierarchy |  PRIMARY KEY CONSTRAINT CLUSTERED | WorkItemHierarchyID |  N/a  |

## Incremental Refresh Policies

- Load all Records once a day