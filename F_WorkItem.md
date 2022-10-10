## Mapping	
								
|ETL Stage	|Source Table	|Source Fields	|Target Field	|Include	|Data Type	|Null	|Default Value	|Model Field	|Type of Field|
| ------------	| ------------	| ------------	| ------------	| ------------	| ------------	| ------------	| ------------	| ------------	| ------------ |
|cast	|	|IDENTITY(1,1)	|WorkItemID	|1	|INT	|0	|-1	|	|pk|
|cast	|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/get-work-item?view=azure-devops-rest-7.1&tabs=HTTP	|fields{System.Title}	|WorkItemDescription	|1	|VARCHAR(50)	|0	|Unknown	|	||
|cast	|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/get-work-item?view=azure-devops-rest-7.1&tabs=HTTP	|fields{System.IterationPath}	|CountofSprints	|1	|INT	|0	|Unknown	|	||
|cast	|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/get-work-item?view=azure-devops-rest-7.1&tabs=HTTP	|fields{Mircosoft.VSTS.Scheduling.OriginalEstimate}	|OriginalEstimate	|1	|INT	|0	|Unknown	|	||
|cast	|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/get-work-item?view=azure-devops-rest-7.1&tabs=HTTP	|fields{Mircosoft.VSTS.SchedulingRemainingWork}	|Remaining	|1	|INT	|1	|Null	|	||
|cast	|https://learn.microsoft.com/en-us/rest/api/azure/devops/wit/work-items/get-work-item?view=azure-devops-rest-7.1&tabs=HTTP	|fields{Mircosoft.VSTS.Scheduling.CompletedWork}	|Completed	|1	|INT	|1	|Null	|	||
|dimension	|table_D_Sprint	|SprintID	|FK_SprintID	|0	|INT	|0	|-1	|FK_SprintID	|fk|
|dimension	|table_D_Person	|PersonID	|FK_PersonID	|0	|INT	|0	|-1	|FK_PersonID	|fk|
|dimension	|table_D_State	|StateID	|FK_StateID	|0	|INT	|0	|-1	|FK_StateID	|fk|
|dimension	|table_D_Priority	|PriorityID	|FK_PriorityID	|0	|INT	|0	|-1	|FK_PriorityID	|fk|
|dimension	|table_D_BlockedReasonTag	|BlockedReasonTagID	|FK_BlockedReasonTagID	|0	|INT	|0	|-1	|FK_BlockedReasonTagID	|fk|
|dimension	|table_D_EnjoymentTag	|EnjoymentTagID	|FK_EnjoymentTagID	|0	|INT	|0	|-1	|FK_EnjoymentTagID	|fk|
|dimension	|table_D_LanguageTag	|LanguageTagID	|FK_LanguageTagID	|0	|INT	|0	|-1	|FK_LanguageTagID	|fk|
|dimension	|table_D_RepoTag	|RepoTagID	|FK_RepoTagID	|0	|INT	|0	|-1	|FK_RepoTagID	|fk|
|dimension	|table_D_Reason	|ReasonID	|FK_ReasonID	|0	|INT	|0	|-1	|FK_ReasonID	|fk|
|dimension	|table_D_WorkItemType	|WorkItemTypeID	|FK_WorkItemTypeID	|0	|INT	|0	|-1	|FK_WorkItemTypeID	|fk|
|dimension	|table_D_WorkItemHierarchy	|WorkItemHierachyID	|FK_WorkItemHierachyID	|0	|INT	|0	|-1	|FK_WorkItemHierachyID	|fk|
|dimension	|table_D_Taskboard	|TaskboardID	|FK_TaskboardID	|0	|INT	|0	|-1	|FK_TaskboardID	|fk|
|dimension	|table_D_Task	|TaskID	|FK_TaskID	|0	|INT	|0	|-1	|FK_TaskID	|fk|
|dimension	|table_D_Date	|DateID	|FK_DateID	|0	|INT	|0	|-1	|FK_DateID	|fk|
									
## Joins
									
|Join Type	|ETL Stage	|Join Table	|Source Table Keys	|Join Table Keys|					
| ------------ |	| ------------	| ------------	| ------------	| ------------ |					
|LEFT	|dimension	|table_D_Sprint	|SprintID	|FK_SprintID|					
|LEFT	|dimension	|table_D_Person	|PersonID	|FK_PersonID|					
|LEFT	|dimension	|table_D_State	|StateID	|FK_StateID|					
|LEFT	|dimension	|table_D_Priority	|PriorityID	|FK_PriorityID|					
|LEFT	|dimension	|table_D_BlockedReasonTag	|BlockedReasonTagID	|FK_BlockedReasonTagID|					
|LEFT	|dimension	|table_D_EnjoymentTag	|EnjoymentTagID	|FK_EnjoymentTagID|					
|LEFT	|dimension	|table_D_LanguageTag	|LanguageTagID	|FK_LanguageTagID|					
|LEFT	|dimension	|table_D_RepoTag	|RepoTagID	|FK_RepoTagID|					
|LEFT	|dimension	|table_D_Reason	|ReasonID	|FK_ReasonID|					
|LEFT	|dimension	|table_D_WorkItemType	|WorkItemTypeID	|FK_WorkItemTypeID|					
|LEFT	|dimension	|table_D_WorkItemHierarchy	|WorkItemHierachyID	|FK_WorkItemHierachyID|					
|LEFT	|dimension	|table_D_Taskboard	|TaskboardID	|FK_TaskboardID|					
|LEFT	|dimension	|table_D_Task	|TaskID	|FK_TaskID|					
|LEFT	|dimension	|table_D_Date	|DateID	|FK_DateID|					
									
## Keys, Indexes, Partitions
									
|Name	|Type	|On	|Including|						
| ------------ |	| ------------	| ------------	| ------------ |						
|PK_WorkItemID	|PRIMARY KEY CONSTRANT CLUSTERED	|WorkItemID	|N/A|						
