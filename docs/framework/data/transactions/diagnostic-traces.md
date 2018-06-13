---
title: 诊断跟踪
ms.date: 03/30/2017
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
ms.openlocfilehash: 56f79fb9140785188996cc413eca4dd530037ccd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363462"
---
# <a name="diagnostic-traces"></a>诊断跟踪
跟踪是指发布在执行应用程序期间生成的特定消息。 使用跟踪时，必须具有收集和记录所发送消息的机制。 跟踪消息由侦听器来接收。 侦听器的用途是收集、存储和路由跟踪消息。 侦听器会将跟踪输出定向到适当的目标，如日志、窗口或文本文件。  
  
 <xref:System.Diagnostics.DefaultTraceListener> 就是一个这样的侦听器，在启用跟踪后将自动创建并初始化它。 如果要将跟踪输出定向到任何其他源，则必须创建并初始化其他跟踪侦听器。 所创建的侦听器应反映您的具体需要。 例如，您可能需要所有跟踪输出的文本记录。 在这种情况下，可以创建一个侦听器，使其在启用时将所有输出写入一个新的文本文件。 另一方面，您可能只需要在执行应用程序的过程中查看输出。 在这种情况下，可以创建一个侦听器，使其将所有输出定向到一个控制台窗口。 <xref:System.Diagnostics.EventLogTraceListener> 可将跟踪输出定向到事件日志，而 <xref:System.Diagnostics.TextWriterTraceListener> 可将跟踪输出写入流中。  
  
## <a name="enabling-tracing"></a>启用跟踪  
 若要在事务处理期间启用跟踪，应编辑应用程序的配置文件。 下面是一个示例。  
  
```xml  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"   
                     type="System.Diagnostics.XmlWriterTraceListener"   
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
```  
  
 <xref:System.Transactions> 跟踪将写入到一个名为“System.Transactions”的源。 可以使用 `add` 指定要使用的跟踪侦听器的名称和类型。 在示例配置中，将侦听器命名为“tx”并添加了标准 .NET Framework 跟踪侦听器 (<xref:System.Diagnostics.XmlWriterTraceListener>) 作为要使用的类型。 使用 `initializeData` 设置该侦听器的日志文件的名称。 此外，还可以用一个简单文件名来替换完全限定路径。  
  
 每个跟踪消息类型都分配有一个指示其重要程度的级别。 如果应用程序域的跟踪级别等于或小于事件类型的级别，就会生成该消息。 跟踪级别由配置文件中的 `switchValue` 设置控制。 下表定义了与诊断跟踪消息关联的级别。  
  
|跟踪级别|描述|  
|-----------------|-----------------|  
|严重|表示发生了类似于下面的严重故障：<br /><br /> 的可以会立即丢失导致用户功能错误。<br />的需要管理员采取措施以避免失去的功能事件。<br />的挂起代码。<br />-此跟踪级别还可为解释其他关键的跟踪提供足够的上下文。 这可以帮助确定导致严重故障的操作序列。|  
|错误|发生了可能会导致用户功能丧失的错误（如无效的配置或网络行为）。|  
|警告|存在一种状况，它可能会在以后导致错误或严重故障（例如，分配失败或达到限制）。 对用户代码中的错误（例如，事务中止、超时、身份验证失败）的正常处理也可能会生成警告。|  
|信息|生成对监视和诊断系统状态、测量性能或执行分析十分有用的消息。 这些消息可包括事务和登记生存期事件，如创建或提交事务、跨重要边界或分配重要资源等。 开发人员可利用此类信息规划容量和管理性能。|  
  
## <a name="trace-codes"></a>跟踪代码  
 下表列出了由 <xref:System.Transactions> 基础结构生成的跟踪代码。 表中包括的跟踪代码标识符，<xref:System.Diagnostics.EventTypeFilter.EventType%2A>跟踪，以及中包含的额外数据的枚举级别**TraceRecord**跟踪的。 此外，跟踪的相应的跟踪级别也存储在**TraceRecord**。  
  
|TraceCode|EventType|TraceRecord 中的额外数据|  
|---------------|---------------|-------------------------------|  
|TransactionCreated|Info|TransactionTraceId|  
|TransactionPromoted|Info|Local TransactionTraceId、Distributed TransactionTraceId|  
|EnlistmentCreated|Info|TransactionTraceId、EnlistmentTraceId、EnlistmentType（持久/可变）、EnlistmentOptions|  
|EnlistmentCallbackNegative|警告|TransactionTraceId、EnlistmentTraceId<br /><br /> Callback (forcerollback/aborted/indoubt)|  
|TransactionRollbackCalled|警告|TransactionTraceId|  
|TransactionAborted|警告|TransactionTraceId|  
|TransactionInDoubt|警告|TransactionTraceId|  
|TransactionScopeCreated|Info|TransactionScopeResult，可为以下各项：<br /><br /> -新事务。<br />-传入的事务。<br />的传入的事务依赖。<br />-使用当前事务。<br />-无事务。<br /><br /> 新的当前 TransactionTraceId|  
|TransactionScopeDisposed|T:System.Diagnostics.Switch|作用域的 TransactionTraceId"应"当前事务。|  
|TransactionScopeIncomplete|警告|作用域的 TransactionTraceId"应"当前事务。|  
|TransactionScopeNestedIncorrectly|警告|作用域的 TransactionTraceId"应"当前事务。|  
|TransactionScopeCurrentTransactionChanged|警告|旧的当前 TransactionTraceId、其他 TransactionTraceId|  
|TransactionScopeTimeout|警告|作用域的 TransactionTraceId"应"当前事务。|  
|DependentCloneCreated|Info|TransactionTraceId、已创建的依赖事务的类型 (RollbackIfNotComplete/BlockCommitUntilComplete)|  
|DependentCloneComplete|Info|TransactionTraceId|  
|RecoveryComplete|Info|资源管理器 GUID（来自基类型）|  
|Reenlist|Info|资源管理器 GUID（来自基类型）|  
|TransactionSerialized|Info|TransactionTraceId。|  
|TransactionException|错误|异常消息|  
|InvalidOperationException|错误|异常消息|  
|InternalError|严重|异常消息|  
|TransferEvent||当事务反序列化或者从 <xref:System.Transactions> 事务提升为分布式事务时，将写入 ExecutionContext 中的当前 ActivityID 以及分布式事务 ID。<br /><br /> 当 DTC 回调到托管代码中时，分布式事务 ID 会在回调期间设置为 ExecutionContext 中的 ActivityID。|  
|ConfiguredDefaultTimeoutAdjusted|警告|没有额外数据|  
|TransactionTimeout|警告|正在超时的事务的 TransactionTraceId。|  
  
 上述每个额外数据项的 XML 架构采用以下格式。  
  
### <a name="transactiontraceidentifier"></a>TransactionTraceIdentifier  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a>EnlistmentTraceIdentifier  
 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### <a name="resource-manager-identifier"></a>资源管理器标识符  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a>跟踪的安全问题  
 当你以管理员身份打开跟踪时，则敏感信息可能会写入到公开可见的跟踪日志中默认情况下。 若要缓解任何可能的安全威胁，应考虑将跟踪日志存储在安全控制由的共享和文件系统访问权限的位置。
