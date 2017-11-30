---
title: "跟踪事件参考"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1c1ee87-f80a-449b-acd0-50d81eef116e
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d54c8bd4c6a73b9ff5b4066832b557041d7dec0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="tracking-events-reference"></a>跟踪事件参考
执行期间，[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中的工作流在逐步经历其生存期内的各个阶段时会引发跟踪事件。 宿主可以订阅这些事件并且在生存期内使工作流的进度状态保持最新。 本节介绍引发的跟踪事件。  
  
## <a name="event-reference"></a>事件参考  
  
|事件 ID|事件级别|事件消息|关键字|  
|--------------|-----------------|-------------------|--------------|  
|[100 - WorkflowInstanceRecord](../../../docs/framework/windows-workflow-foundation/100-workflowinstancerecord.md)|信息|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[101 - WorkflowInstanceUnhandledExceptionRecord](../../../docs/framework/windows-workflow-foundation/101-workflowinstanceunhandledexceptionrecord.md)|错误|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9, Annotations= %10, ProfileName = %11|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[102 - WorkflowInstanceAbortedRecord](../../../docs/framework/windows-workflow-foundation/102-workflowinstanceabortedrecord.md)|警告|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[103 - ActivityStateRecord](../../../docs/framework/windows-workflow-foundation/103-activitystaterecord.md)|信息|TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[104 - ActivityScheduledRecord](../../../docs/framework/windows-workflow-foundation/104-activityscheduledrecord.md)|信息|TrackRecord = ActivityScheduledRecord, InstanceID = %1,  RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[105 - FaultPropagationRecord](../../../docs/framework/windows-workflow-foundation/105-faultpropagationrecord.md)|警告|TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[106 - CancelRequestRecord](../../../docs/framework/windows-workflow-foundation/106-cancelrequestrecord.md)|信息|TrackRecord = CancelRequestedRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[107 -- BookmarkResumptionRecord](../../../docs/framework/windows-workflow-foundation/107-bookmarkresumptionrecord.md)|信息|TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5,  OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[108 - CustomTrackingRecordInfo](../../../docs/framework/windows-workflow-foundation/108-customtrackingrecordinfo.md)|信息|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents、EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[110 - CustomTrackingRecordWarning](../../../docs/framework/windows-workflow-foundation/110-customtrackingrecordwarning.md)|警告|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents、EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[111 - CustomTrackingRecordError](../../../docs/framework/windows-workflow-foundation/111-customtrackingrecorderror.md)|错误|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents、EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[112 - WorkflowInstanceSuspendedRecord](../../../docs/framework/windows-workflow-foundation/112-workflowinstancesuspendedrecord.md)|信息|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[113 - WorkflowInstanceTerminatedRecord](../../../docs/framework/windows-workflow-foundation/113-workflowinstanceterminatedrecord.md)|错误|TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[114 - WorkflowInstanceRecordWithId](../../../docs/framework/windows-workflow-foundation/114-workflowinstancerecordwithid.md)|信息|TrackRecord= WorkflowInstanceRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，State = %5，Annotations = %6， ProfileName = %7，WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[115 - WorkflowInstanceAbortedRecordWithId](../../../docs/framework/windows-workflow-foundation/115-workflowinstanceabortedrecordwithid.md)|警告|TrackRecord = WorkflowInstanceAbortedRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，Reason = %5，Annotations = %6，ProfileName = %7，WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[116 - WorkflowInstanceSuspendedRecordWithId](../../../docs/framework/windows-workflow-foundation/116-workflowinstancesuspendedrecordwithid.md)|信息|TrackRecord = WorkflowInstanceSuspendedRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，Reason = %5，Annotations = %6，ProfileName = %7，WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[117 - WorkflowInstanceTerminatedRecordWithId](../../../docs/framework/windows-workflow-foundation/117-workflowinstanceterminatedrecordwithid.md)|错误|TrackRecord = WorkflowInstanceTerminatedRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，Reason = %5，Annotations = %6，ProfileName = %7，WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[118 - WorkflowInstanceUnhandledExceptionRecordWithId](../../../docs/framework/windows-workflow-foundation/118-workflowinstanceunhandledexceptionrecordwithid.md)|错误|TrackRecord = WorkflowInstanceUnhandledExceptionRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，SourceName = %5，SourceId = %6，SourceInstanceId = %7，SourceTypeName = %8，Exception = %9，Annotations = %10，ProfileName =%11，WorkflowDefinitionIdentity = %12|HealthMonitoring、WFTrackingHealthMonitoring、WFTracking|  
|[119 - WorkflowInstanceUpdatedRecord](../../../docs/framework/windows-workflow-foundation/119-workflowinstanceupdatedrecord.md)|信息|TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9|HealthMonitoring、WFTracking|  
|[225 - TraceCorrelationKeys](../../../docs/framework/windows-workflow-foundation/225-tracecorrelationkeys.md)|信息|使用父作用域“%3”中的值“%2”计算出的相关键“%1”。|WFServices 疑难解答|  
|[440 - StartSignpostEvent1](../../../docs/framework/windows-workflow-foundation/440-startsignpostevent.md)|信息|活动边界。|WFServices 疑难解答|  
|[441- StopSignpostEvent1](../../../docs/framework/windows-workflow-foundation/441-stopsignpostevent.md)|信息|活动边界。|WFServices 疑难解答|  
|[1001 - WorkflowApplicationCompleted](../../../docs/framework/windows-workflow-foundation/1001-workflowapplicationcompleted.md)|信息|WorkflowInstance Id“%1”在“已关闭”状态下完成。|WFRuntime|  
|[1002 - WorkflowApplicationTerminated](../../../docs/framework/windows-workflow-foundation/1002-workflowapplicationterminated.md)|信息|WorkflowApplication Id“%1”已终止。 该应用程序因出现异常而在“出错”状态下完成。|WFRuntime|  
|[1003 - WorkflowInstanceCanceled](../../../docs/framework/windows-workflow-foundation/1003-workflowinstancecanceled.md)|信息|WorkflowInstance Id“%1”在“已取消”状态下完成。|WFRuntime|  
|[1004 - WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md)|信息|WorkflowInstance Id“%1”因出现异常而中止。|WFRuntime|  
|[1005 - WorkflowApplicationIdled](../../../docs/framework/windows-workflow-foundation/1005-workflowapplicationidled.md)|信息|WorkflowApplication ID“%1”变为空闲状态。|WFRuntime|  
|[1006 - WorkflowApplicationUnhandledException](../../../docs/framework/windows-workflow-foundation/1006-workflowapplicationunhandledexception.md)|错误|WorkflowInstance Id"%1"遇到未经处理的异常。  则将产生异常从 Activity"%2"、 DisplayName:"%3"。  不会执行以下操作: %4。|WFRuntime|  
|[1007 - WorkflowApplicationPersisted](../../../docs/framework/windows-workflow-foundation/1007-workflowapplicationpersisted.md)|信息|WorkflowApplication ID“%1”已持久化。|WFRuntime|  
|[1008 - WorkflowApplicationUnloaded](../../../docs/framework/windows-workflow-foundation/1008-workflowapplicationunloaded.md)|信息|WorkflowInstance Id“%1”已卸载。|WFRuntime|  
|[1009 - ActivityScheduled](../../../docs/framework/windows-workflow-foundation/1009-activityscheduled.md)|信息|父 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了子 Activity“%4”、DisplayName“%5”、InstanceId“%6”。|WFRuntime|  
|[1010 - ActivityCompleted](../../../docs/framework/windows-workflow-foundation/1010-activitycompleted.md)|信息|父 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了子 Activity“%4”、DisplayName“%5”、InstanceId“%6”。|WFRuntime|  
|[1011 - ScheduleExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1011-scheduleexecuteactivityworkitem.md)|详细|已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 ExecuteActivityWorkItem。|WFRuntime|  
|[1012 - StartExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1012-startexecuteactivityworkitem.md)|详细|开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 ExecuteActivityWorkItem。|WFRuntime|  
|[1013 - CompleteExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1013-completeexecuteactivityworkitem.md)|详细|Activity“%1”、DisplayName“%2”、InstanceId“%3”的 ExecuteActivityWorkItem 已经完成。|WFRuntime|  
|[1014 - ScheduleCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1014-schedulecompletionworkitem.md)|详细|CompletionWorkItem 已安排为父 Activity"%1"、 DisplayName:"%2"、 InstanceId:"%3"。  已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。|WFRuntime|  
|[1015 - StartCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1015-startcompletionworkitem.md)|详细|开始为父 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CompletionWorkItem。 已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。|WFRuntime|  
|[1016 - CompleteCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1016-completecompletionworkitem.md)|详细|父 Activity“%1”、DisplayName“'%2”、InstanceId“%3”已完成了 CompletionWorkItem。 已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。|WFRuntime|  
|[1017 - ScheduleCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1017-schedulecancelactivityworkitem.md)|详细|已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 CancelActivityWorkItem。|WFRuntime|  
|[1018 - StartCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1018-startcancelactivityworkitem.md)|详细|开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CancelActivityWorkItem。|WFRuntime|  
|[1019 - CompleteCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1019-completecancelactivityworkitem.md)|详细|Activity“%1”、DisplayName“%2”、InstanceId“%3”的 CancelActivityWorkItem 已经完成。|WFRuntime|  
|[1020 - CreateBookmark](../../../docs/framework/windows-workflow-foundation/1020-createbookmark.md)|详细|已为 Activity"%1"、 DisplayName 创建书签:"%2"、 InstanceId:"%3"。  BookmarkName: %4、BookmarkScope: %5。|WFRuntime|  
|[1021 - ScheduleBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1021-schedulebookmarkworkitem.md)|详细|已为 Activity"%1"、 DisplayName 安排 BookmarkWorkItem:"%2"、 InstanceId:"%3"。  BookmarkName: %4、BookmarkScope: %5。|WFRuntime|  
|[1022 - StartBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1022-startbookmarkworkitem.md)|详细|开始执行的活动 DisplayName"%1"的 BookmarkWorkItem:"%2"、 InstanceId:"%3"。  BookmarkName: %4、BookmarkScope: %5。|WFRuntime|  
|[1023 - CompleteBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1023-completebookmarkworkitem.md)|详细|Activity“%1”、DisplayName“%2”、InstanceId“%3”的 BookmarkWorkItem 已经完成。 BookmarkName: %4、BookmarkScope: %5。|WFRuntime|  
|[1024 - CreateBookmarkScope](../../../docs/framework/windows-workflow-foundation/1024-createbookmarkscope.md)|详细|已创建 BookmarkScope: %1。|WFRuntime|  
|[1025 - BookmarkScopeInitialized](../../../docs/framework/windows-workflow-foundation/1025-bookmarkscopeinitialized.md)|详细|TemporaryId 为“%1”的 BookmarkScope 已初始化，ID 为:“%2”。|WFRuntime|  
|[1026 - ScheduleTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1026-scheduletransactioncontextworkitem.md)|详细|已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 TransactionContextWorkItem。|WFRuntime|  
|[1027 - StartTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1027-starttransactioncontextworkitem.md)|详细|开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 TransactionContextWorkItem。|WFRuntime|  
|[1028 - CompleteTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1028-completetransactioncontextworkitem.md)|详细|Activity“%1”、DisplayName“%2”、InstanceId“%3”的 TransactionContextWorkItem 已经完成。|WFRuntime|  
|[1029 - ScheduleFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1029-schedulefaultworkitem.md)|详细|已为 Activity"%1"、 DisplayName 安排 FaultWorkItem:"%2"、 InstanceId:"%3"。  异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。|WFRuntime|  
|[1030 - StartFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1030-startfaultworkitem.md)|详细|开始执行的活动 DisplayName"%1"的 FaultWorkItem:"%2"、 InstanceId:"%3"。  异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。|WFRuntime|  
|[1031 - CompleteFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1031-completefaultworkitem.md)|详细|Activity“%1”、DisplayName“%2”、InstanceId“%3”的 FaultWorkItem 已经完成。 异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。|WFRuntime|  
|[1032 - ScheduleRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1032-scheduleruntimeworkitem.md)|详细|已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了运行时工作项。|WFRuntime|  
|[1033 - StartRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1033-startruntimeworkitem.md)|详细|开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行运行时工作项。|WFRuntime|  
|[1034 - CompleteRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1034-completeruntimeworkitem.md)|详细|Activity“%1”、DisplayName“%2”、InstanceId“%3”的运行时工作项已经完成。|WFRuntime|  
|[1035 - RuntimeTransactionSet](../../../docs/framework/windows-workflow-foundation/1035-runtimetransactionset.md)|详细|运行时事务已设置 Activity"%1"、 DisplayName:"%2"、 InstanceId:"%3"。  执行隔离到活动"%4"、 DisplayName:"%5"、 InstanceId:"%6"。|WFRuntime|  
|[1036 - RuntimeTransactionCompletionRequested](../../../docs/framework/windows-workflow-foundation/1036-runtimetransactioncompletionrequested.md)|详细|Activity“%1”、DisplayName“%2”、InstanceId“%3”已安排了运行时事务的完成。|WFRuntime|  
|[1037 - RuntimeTransactionComplete](../../../docs/framework/windows-workflow-foundation/1037-runtimetransactioncomplete.md)|详细|运行时事务已完成，状态为“%1”。|WFRuntime|  
|[1038 - EnterNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1038-enternopersistblock.md)|详细|正在进入非持久块。|WFRuntime|  
|[1039 - ExitNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1039-exitnopersistblock.md)|详细|正在退出非持久块。|WFRuntime|  
|[1040 - InArgumentBound](../../../docs/framework/windows-workflow-foundation/1040-inargumentbound.md)|详细|Activity“%2”、DisplayName“%3”、InstanceId“%4”中的 In 参数“%1”已经与值 %5 绑定。|WFActivities|  
|[1041 - WorkflowApplicationPersistableIdle](../../../docs/framework/windows-workflow-foundation/1041-workflowapplicationpersistableidle.md)|信息|WorkflowApplication Id ' %1' 是空闲且可持久化。  不会执行以下操作: %2。|WFRuntime|  
|[1101 - WorkflowActivityStart](../../../docs/framework/windows-workflow-foundation/1101-workflowactivitystart.md)|信息|WorkflowInstance Id“%1”E2E 活动|WFRuntime|  
|[1102 - WorkflowActivityStop](../../../docs/framework/windows-workflow-foundation/1102-workflowactivitystop.md)|信息|WorkflowInstance Id“%1”E2E 活动|WFRuntime|  
|[1103 - WorkflowActivitySuspend](../../../docs/framework/windows-workflow-foundation/1103-workflowactivitysuspend.md)|信息|WorkflowInstance Id“%1”E2E 活动|WFRuntime|  
|[1104 - WorkflowActivityResume](../../../docs/framework/windows-workflow-foundation/1104-workflowactivityresume.md)|信息|WorkflowInstance Id“%1”E2E 活动|WFRuntime|  
|[1124 - InvokeMethodIsStatic](../../../docs/framework/windows-workflow-foundation/1124-invokemethodisstatic.md)|信息|InvokeMethod“%1”- 方法为静态。|WFRuntime|  
|[1125 - InvokeMethodIsNotStatic](../../../docs/framework/windows-workflow-foundation/1125-invokemethodisnotstatic.md)|信息|InvokeMethod“%1”- 方法非静态。|WFRuntime|  
|[1126 - InvokedMethodThrewException](../../../docs/framework/windows-workflow-foundation/1126-invokedmethodthrewexception.md)|信息|在活动“%1”调用的方法中，引发了异常。 %2|WFRuntime|  
|[1131 - InvokeMethodUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1131-invokemethoduseasyncpattern.md)|信息|InvokeMethod“%1”- 方法使用“%2”和“%3”的异步模式。|WFRuntime|  
|[1132 - InvokeMethodDoesNotUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1132-invokemethoddoesnotuseasyncpattern.md)|信息|InvokeMethod“%1”- 方法不使用异步模式。|WFRuntime|  
|[1140 - FlowchartStart](../../../docs/framework/windows-workflow-foundation/1140-flowchartstart.md)|信息|Flowchart“%1”- 已安排启动。|WFActivities|  
|[1141 - FlowchartEmpty](../../../docs/framework/windows-workflow-foundation/1141-flowchartempty.md)|警告|Flowchart“%1”- 在无节点的情况下执行。在活动“%1”调用的方法中，引发了异常。 %2|WFActivities|  
|[1143 - FlowchartNextNull](../../../docs/framework/windows-workflow-foundation/1143-flowchartnextnull.md)|信息|Flowchart“%1”/FlowStep - 下一个节点为 null。 Flowchart 执行将结束。|WFActivities|  
|[1146 - FlowchartSwitchCase](../../../docs/framework/windows-workflow-foundation/1146-flowchartswitchcase.md)|信息|Flowchart“%1”/FlowSwitch - 选择了 Case“%2”。|WFActivities|  
|[1147 - FlowchartSwitchDefault](../../../docs/framework/windows-workflow-foundation/1147-flowchartswitchdefault.md)|信息|Flowchart“%1”/FlowSwitch - 选择了 Default Case。|WFActivities|  
|[1148 - FlowchartSwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1148-flowchartswitchcasenotfound.md)|信息|Flowchart“%1”/FlowSwitch - 找不到 Case 活动，也找不到与 Expression 结果匹配的 Default Case。 Flowchart 执行将结束。|WFActivities|  
|[1150 - CompensationState](../../../docs/framework/windows-workflow-foundation/1150-compensationstate.md)|信息|CompensableActivity“%1”的状态为“%2”。|WFActivities|  
|[1223 - SwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1223-switchcasenotfound.md)|信息|Switch 活动“%1”找不到与 Expression 结果匹配的 Case 活动。|WFActivities|  
|[1449 - WfMessageReceived](../../../docs/framework/windows-workflow-foundation/1449-wfmessagereceived.md)|信息|工作流已接收消息|WFServices|  
|[1450 - WfMessageSent](../../../docs/framework/windows-workflow-foundation/1450-wfmessagesent.md)|信息|已从工作流发送消息|WFServices|  
|[2021 - ExecuteWorkItemStart](../../../docs/framework/windows-workflow-foundation/2021-executeworkitemstart.md)|详细|开始执行工作项|WFRuntime|  
|[2022 - ExecuteWorkItemStop](../../../docs/framework/windows-workflow-foundation/2022-executeworkitemstop.md)|详细|停止执行工作项|WFRuntime|  
|[2023 - SendMessageChannelCacheMiss](../../../docs/framework/windows-workflow-foundation/2023-sendmessagechannelcachemiss.md)|详细|SendMessageChannelCache 未命中|WFRuntime|  
|[2024 - InternalCacheMetadataStart](../../../docs/framework/windows-workflow-foundation/2024-internalcachemetadatastart.md)|详细|已在活动“%1”上启动 InternalCacheMetadata。|WFRuntime|  
|[2025 - InternalCacheMetadataStop](../../../docs/framework/windows-workflow-foundation/2025-internalcachemetadatastop.md)|详细|已在活动“%1”上停止 InternalCacheMetadata。|WFRuntime|  
|[2026 - CompileVbExpressionStart](../../../docs/framework/windows-workflow-foundation/2026-compilevbexpressionstart.md)|详细|正在编译 VB 表达式“%1”|WFRuntime|  
|[2027 - CacheRootMetadataStart](../../../docs/framework/windows-workflow-foundation/2027-cacherootmetadatastart.md)|详细|已在活动“%1”上启动 CacheRootMetadata|WFRuntime|  
|[2028 - CacheRootMetadataStop](../../../docs/framework/windows-workflow-foundation/2028-cacherootmetadatastop.md)|详细|已在活动 %1 上停止 CacheRootMetadata。|WFRuntime|  
|[2029 - CompileVbExpressionStop](../../../docs/framework/windows-workflow-foundation/2029-compilevbexpressionstop.md)|详细|已完成编译 VB 表达式。|WFRuntime|  
|[2576 - TryCatchExceptionFromTry](../../../docs/framework/windows-workflow-foundation/2576-trycatchexceptionfromtry.md)|信息|TryCatch 活动“%1”捕获了“%2”类型的异常。|WFActivities|  
|[2577 - TryCatchExceptionDuringCancelation](../../../docs/framework/windows-workflow-foundation/2577-trycatchexceptionduringcancelation.md)|警告|TryCatch 活动“%1”的子活动在取消过程中引发了异常。|WFActivities|  
|[2578 - TryCatchExceptionFromCatchOrFinally](../../../docs/framework/windows-workflow-foundation/2578-trycatchexceptionfromcatchorfinally.md)|警告|与 TryCatch 活动“%1”关联的 Catch 或 Finally 活动引发了异常。|WFActivities|  
|[3501 - InferredContractDescription](../../../docs/framework/windows-workflow-foundation/3501-inferredcontractdescription.md)|信息|已从 WorkflowService 中推断出含有 Name 为“%1”和 Namespace 为“%2”的 ContractDescription。|WFServices|  
|[3502 - InferredOperationDescription](../../../docs/framework/windows-workflow-foundation/3502-inferredoperationdescription.md)|信息|已从 WorkflowService 中推断出协定“%2”中含有 Name='%1' 的 OperationDescription。 IsOneWay=%3。|WFServices|  
|[3503 - DuplicateCorrelationQuery](../../../docs/framework/windows-workflow-foundation/3503-duplicatecorrelationquery.md)|警告|找到了含有 Where='%1' 的重复 CorrelationQuery。 计算相关性时将不使用此重复查询。|WFServices|  
|[3507 - ServiceEndpointAdded](../../../docs/framework/windows-workflow-foundation/3507-serviceendpointadded.md)|信息|已为地址“%1”、绑定“%2”和协定“%3”添加了服务终结点。|WFServices|  
|[3508 - TrackingProfileNotFound](../../../docs/framework/windows-workflow-foundation/3508-trackingprofilenotfound.md)|详细|未找到 ActivityDefinitionId“%2”的 TrackingProfile“%1”。 在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 不匹配。|WFServices|  
|[3550 - BufferOutOfOrderMessageNoInstance](../../../docs/framework/windows-workflow-foundation/3550-bufferoutofordermessagenoinstance.md)|信息|此时不能执行操作“%1”。 服务实例准备好处理此特定操作时，将进行另一个尝试。|WFServices|  
|[3551 - BufferOutOfOrderMessageNoBookmark](../../../docs/framework/windows-workflow-foundation/3551-bufferoutofordermessagenobookmark.md)|信息|此时不能执行服务实例“%1”上的操作“%2”。 服务实例准备好处理此特定操作时，将进行另一个尝试。|WFServices|  
|[3552 - MaxPendingMessagesPerChannelExceeded](../../../docs/framework/windows-workflow-foundation/3552-maxpendingmessagesperchannelexceeded.md)|警告|已达到了中止值 maxpendingmessagesperchannel 的"%1"。 若要增加此限制，请调整 BufferedReceiveServiceBehavior 中的 MaxPendingMessagesPerChannel 属性。|配额 WFServices|  
|[3557 - TransactedReceiveScopeEndCommitFailed](../../../docs/framework/windows-workflow-foundation/3557-transactedreceivescopeendcommitfailed.md)|信息|ID 为“%1”的 CommittableTransaction 上的 EndCommit 调用引发了具有以下消息的 TransactionException:“%2”。|WFServices|  
|[4201 - EndSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4201-endsqlcommandexecute.md)|详细|结束 SQL 命令执行: %1|WFInstanceStore|  
|[4202 - StartSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4202-startsqlcommandexecute.md)|详细|正在开始 SQL 命令执行: %1|WFInstanceStore|  
|[4203 - RenewLockSystemError](../../../docs/framework/windows-workflow-foundation/4203-renewlocksystemerror.md)|错误|未能延长锁定到期日，锁定到期日已过，或者已删除锁定所有者。 正在中止 SqlWorkflowInstanceStore。|WFInstanceStore|  
|[4205 - FoundProcessingError](../../../docs/framework/windows-workflow-foundation/4205-foundprocessingerror.md)|错误|命令失败: %1|WFInstanceStore|  
|[4206 - UnlockInstanceException](../../../docs/framework/windows-workflow-foundation/4206-unlockinstanceexception.md)|错误|尝试解除实例锁定时遇到异常 %1。|WFInstanceStore|  
|[4207 - MaximumRetriesExceededForSqlCommand](../../../docs/framework/windows-workflow-foundation/4207-maximumretriesexceededforsqlcommand.md)|信息|正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。|配额 FInstanceStore|  
|[4208 - RetryingSqlCommandDueToSqlError](../../../docs/framework/windows-workflow-foundation/4208-retryingsqlcommandduetosqlerror.md)|信息|因 SQL 错误号 %1，正在重试 SQL 命令。|WFInstanceStore|  
|[4209 - TimeoutOpeningSqlConnection](../../../docs/framework/windows-workflow-foundation/4209-timeoutopeningsqlconnection.md)|错误|尝试打开 SQL 连接时超时。 操作在分配的超时 %1 内没有完成。 分配给此操作的时间可能是更长超时的一部分。|WFInstanceStore|  
|[4210 - SqlExceptionCaught](../../../docs/framework/windows-workflow-foundation/4210-sqlexceptioncaught.md)|警告|已捕获 SQL 异常编号为 %1 的消息 %2。|WFInstanceStore|  
|[4211 - QueuingSqlRetry](../../../docs/framework/windows-workflow-foundation/4211-queuingsqlretry.md)|警告|正在将 SQL 重试排队，延迟 %1 毫秒。|WFInstanceStore|  
|[4212 - LockRetryTimeout](../../../docs/framework/windows-workflow-foundation/4212-lockretrytimeout.md)|警告|尝试获取实例锁超时。  操作在分配的超时 %1 内没有完成。 分配给此操作的时间可能是更长超时的一部分。|WFInstanceStore|  
|[4213 - RunnableInstancesDetectionError](../../../docs/framework/windows-workflow-foundation/4213-runnableinstancesdetectionerror.md)|错误|由于下列异常，导致可运行实例检测失败|WFInstanceStore|  
|[4214 - InstanceLocksRecoveryError](../../../docs/framework/windows-workflow-foundation/4214-instancelocksrecoveryerror.md)|错误|由于下列异常，导致实例锁恢复失败|WFInstanceStore|  
|[39456 - TrackingRecordDropped](../../../docs/framework/windows-workflow-foundation/39456-trackingrecorddropped.md)|警告|跟踪记录 %1 的大小超出了 ETW 会话对提供程序 %2 允许的最大值|WFTracking|  
|[39457 - TrackingRecordRaised](../../../docs/framework/windows-workflow-foundation/39457-trackingrecordraised.md)|信息|跟踪记录 %1 提升为 %2。|WFRuntime|  
|[39458 - TrackingRecordTruncated](../../../docs/framework/windows-workflow-foundation/39458-trackingrecordtruncated.md)|警告|用提供程序 %2 向 ETW 会话写入了截断的跟踪记录 %1。 已移除了变量/批注/用户数据|WFTracking|  
|[39459 - TrackingDataExtracted](../../../docs/framework/windows-workflow-foundation/39459-trackingdataextracted.md)|详细|正在跟踪在活动 %2 中提取的数据 %1。|WFRuntime|  
|[39460 - TrackingValueNotSerializable](../../../docs/framework/windows-workflow-foundation/39460-trackingvaluenotserializable.md)|警告|所提取的参数/变量“%1”不可序列化。|WFTracking|  
|[57398 - MaxInstancesExceeded](../../../docs/framework/windows-workflow-foundation/57398-maxinstancesexceeded.md)|警告|系统达到为限制“MaxConcurrentInstances”设置的限制值。 此限制的限制值设置为 %1。 可通过修改 serviceThrottle 元素中的特性“maxConcurrentInstances”或修改行为 ServiceThrottlingBehavior 的“MaxConcurrentInstances”属性来更改限制值。|WFServices|
