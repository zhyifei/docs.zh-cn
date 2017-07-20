---
title: "任务并行库和 PLINQ 中的 ETW 事件 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "任务，ETW 事件"
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 任务并行库和 PLINQ 中的 ETW 事件
任务并行库和 PLINQ 都会生成 Windows 事件跟踪 \(ETW\) 事件，可以利用此事件通过各种工具（如 Windows 性能分析器）来分析应用程序并对其进行疑难解答。  但在大多数情况下，分析并行应用程序代码的最佳方式是使用[!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)]中的[并发可视化工具](../Topic/Concurrency%20Visualizer.md)。  
  
## 任务并行库 ETW 事件  
 在 EVENT\_HEADER 结构中，由 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>、<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 和 <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=fullName> 生成的事件的 ProviderId GUID 为：  
  
```  
0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5  
```  
  
### 并行循环开始  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### 用户数据  
  
|**名称**|**类型**|**说明**|  
|------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|启动循环的 TaskScheduler 的 ID。|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|启动循环的任务的 ID。|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|唯一的标识符，用于为具有分叉\/联接语义的事件指示嵌套和成对。|  
|OperationType|<xref:System.Int32?displayProperty=fullName>|指示循环的类型：<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|InclusiveFrom|<xref:System.Int64?displayProperty=fullName>|循环计数器的起始值|  
|ExclusiveTo|<xref:System.Int64?displayProperty=fullName>|循环计数器的结束值|  
  
### 并行循环结束  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### 用户数据  
  
|**名称**|**类型**|**说明**|  
|------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|启动循环的 TaskScheduler 的 ID。|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|启动循环的任务的 ID。|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|唯一的标识符，用于为具有分叉\/联接语义的事件指示嵌套和成对。|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|迭代总次数|  
  
### 并行调用开始  
 EVENT\_DESCRIPTOR.Task \= 3  
  
 EVENT\_DESCRIPTOR.Id \= 3  
  
#### 用户数据  
  
|**名称**|**类型**|**说明**|  
|------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|启动循环的 TaskScheduler 的 ID。|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|启动循环的任务的 ID。|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|唯一的标识符，用于为具有分叉\/联接语义的事件指示嵌套和成对。|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|迭代总次数|  
|OperationType|<xref:System.Int32?displayProperty=fullName>|指示循环的类型：<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|ActionCount|<xref:System.Int32?displayProperty=fullName>|在并行调用中将执行的操作数。|  
  
### 并行调用结束  
 EVENT\_DESCRIPTOR.Task \= 4  
  
 EVENT\_DESCRIPTOR.Id \= 4  
  
#### 用户数据  
  
|**名称**|**类型**|**说明**|  
|------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|启动循环的 TaskScheduler 的 ID。|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|启动循环的任务的 ID。|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|唯一的标识符，用于为具有分叉\/联接语义的事件指示嵌套和成对。|  
  
## PLINQ ETW 事件  
 PLINQ 的 EVENT\_HEADER.ProviderId GUID 为：  
  
```  
0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87  
```  
  
### 并行查询开始  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### 用户数据  
  
|**名称**|**类型**|**说明**|  
|------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|启动循环的 TaskScheduler 的 ID。|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|启动循环的任务的 ID。|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|唯一的查询标识符。|  
  
### 并行查询结束  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### 用户数据  
  
|**名称**|**类型**|**说明**|  
|------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|启动循环的 TaskScheduler 的 ID。|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|启动循环的任务的 ID。|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|唯一的查询标识符。|  
  
## 请参阅  
 [.NET Framework 中的 ETW 事件](../../../docs/framework/performance/etw-events.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)