---
title: "Windows Workflow Foundation 功能详细信息 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Windows Workflow Foundation 功能详细信息
[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] 向 Windows Workflow Foundation 添加了大量功能。本文档介绍了大量新的功能，并详述了这些功能可用于的方案。  
  
## 消息传递活动  
 消息传递活动（<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.SendReply>、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.ReceiveReply>）用于通过工作流发送和接收 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 消息。<xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 活动用于构成 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务操作，此操作与标准 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Web 服务一样通过 WSDL 公开。<xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.ReceiveReply> 用于使用与 WCF <xref:System.ServiceModel.ChannelFactory> 类似的 Web 服务；生成预配置的活动的 Workflow Foundation 也具有**“添加服务引用”**体验。  
  
### 消息传递活动入门  
  
-   在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个 WCF 工作流服务应用程序项目。<xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 对将置于画布上。  
  
-   右击该项目并选择**“添加服务引用”**。指向现有 Web 服务 WSDL 并单击**“确定”**。构建您的项目以在工具箱中显示生成的活动（使用 <xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.ReceiveReply> 实现）。  
  
-   这些活动的示例可在以下部分找到：  
  
    -   基本：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   方案：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
-   [概念文档](http://go.microsoft.com/fwlink/?LinkId=204801)  
  
-   [消息传递活动设计器文档](http://go.microsoft.com/fwlink/?LinkId=204802)  
  
### 消息传递活动示例方案  
 `BestPriceFinder` 服务将调用多个航空公司服务来查找特定航线的最佳票价。实现此方案需要您使用消息传递活动来接收价格请求、从后端服务检索价格以及向价格请求回复最佳价格。它还需要您使用其他现有活动来创建用于计算最佳价格的业务逻辑。  
  
## WorkflowServiceHost  
 <xref:System.ServiceModel.WorkflowServiceHost> 是现有工作流主机，它支持多个实例、配置和 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 消息传递（尽管工作流不需要使用消息传递即可承载）。它还通过一组服务行为将持久性、跟踪和实例控件集于一身。与 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 的 <xref:System.ServiceModel.ServiceHost> 一样，<xref:System.ServiceModel.WorkflowServiceHost> 可在控制台\/WinForms\/WPF 应用程序或 Windows 服务中自承载，或在 IIS 或 WAS 中进行 Web 承载（作为 .xamlx 文件）。  
  
### 工作流服务主机入门  
  
-   在 Visual Studio 2010 中，创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 工作流服务应用程序项目：此项目将设置为在 Web 承载环境中使用 <xref:System.ServiceModel.WorkflowServiceHost>。  
  
-   若要承载非消息传递工作流，请添加一个自定义 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>，它将创建基于消息的实例。  
  
-   工作流实例可以控制 （例如暂停或终止） 通过添加 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> 到 <xref:System.ServiceModel.WorkflowServiceHost>，然后使用  <xref:System.ServiceModel.Activities.WorkflowControlClient>。  
  
-   <xref:System.ServiceModel.WorkflowServiceHost> 的示例可在以下部分找到：  
  
    -   [执行](../../../docs/framework/windows-workflow-foundation/samples/execution.md)  
  
    -   基本：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   方案：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   应用程序：[挂起的实例管理](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)  
  
-   [WorkflowServiceHost 概念文档](http://go.microsoft.com/fwlink/?LinkId=204807)  
  
### WorkflowServiceHost 方案  
 BestPriceFinder 服务将调用多个航空公司服务来查找特定路线的最佳票价。实现此方案需要您在 <xref:System.ServiceModel.WorkflowServiceHost> 中承载工作流。它还使用消息传递活动来接收价格请求、从后端服务检索价格以及向价格请求回复最佳价格。  
  
## 相关性  
 相关性具有以下两种含义：  
  
-   将消息组合在一起的方法；即，请求消息与其答复之间的关系。  
  
-   将一段数据映射到一个服务实例的方法  
  
### 入门  
  
-   若要开始学习相关性，请在 Visual Studio 中创建一个新项目。创建一个类型为 <xref:System.ServiceModel.Activities.CorrelationHandle> 的变量。  
  
-   例如，将消息组合在一起的请求\-答复相关性就是用于将消息组合在一起的相关性。  
  
    -   在 <xref:System.ServiceModel.Activities.Receive> 活动上单击 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 属性，并使用上一个步骤中创建的 CorrelationHandle 添加 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>。  
  
    -   通过右击 <xref:System.ServiceModel.Activities.Receive>，再单击“创建 SendReply”来创建 <xref:System.ServiceModel.Activities.SendReply> 活动。将其粘贴到工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动后。  
  
-   将一段数据映射到一个服务实例的示例为基于内容的相关性，它将一段数据（例如，订单 ID）映射到一个特定的工作流实例。  
  
    -   在任何消息传递活动上，单击 `CorrelationInitializers` 属性，并使用上面创建的 <xref:System.ServiceModel.Activities.CorrelationHandle> 变量添加 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>。双击消息上所需的属性 （例如订单 ID） 从下拉菜单。将 `CorrelatesWith` 属性设置为上面使用的 <xref:System.ServiceModel.Activities.CorrelationHandle> 变量。  
  
-   示例：  
  
    -   基本：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   方案：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   [相关性概念文档](http://go.microsoft.com/fwlink/?LinkId=204939)  
  
### 相关性方案  
 订单处理工作流用于处理新订单创建和更新正在处理的现有订单。实现此方案需要您在 <xref:System.ServiceModel.WorkflowServiceHost> 中承载工作流并使用消息传递活动，还需要基于 `orderId` 的相关性以确保对正确工作流进行更新。  
  
## 简化配置  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 配置架构比较复杂，导致用户难以查找功能。在 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中，我们侧重于帮助 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用户使用以下功能来配置其服务：  
  
-   使用户不需要为每个服务进行显式配置。如果未为服务配置任何 \<service\> 元素，并且服务未以编程方式定义任何终结点，则会向服务自动添加一组终结点，每个服务基址和服务实现的每个协定各对应一个终结点。  
  
-   使用户能够为 WCF 绑定和行为定义默认值，这些默认值将应用于无显示配置的服务。  
  
-   标准终结点定义了可重用的预配置终结点，这些终结点具有一个或多个终结点属性（地址、绑定和协定）的固定值，并允许定义自定义属性。  
  
-   最后，<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 允许您对 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端配置进行集中管理，这在应用程序域加载时间后选择或更改配置的方案中很有用。  
  
### 入门  
  
-   [WCF 4.0 开发人员指南](http://go.microsoft.com/fwlink/?LinkId=204940)  
  
-   [配置通道工厂](http://go.microsoft.com/fwlink/?LinkId=204941)  
  
-   [标准终结点元素](http://go.microsoft.com/fwlink/?LinkId=204942)  
  
-   [.NET Framework 4 中的服务配置改进](http://go.microsoft.com/fwlink/?LinkId=204943)  
  
-   [.NET 4 中的常见用户错误：WF\/WCF 服务配置名称键入错误](http://go.microsoft.com/fwlink/?LinkId=204944)  
  
### 简化配置方案  
  
-   一位经验丰富的 ASMX 开发人员希望开始使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]。然而，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 看起来太复杂！我需要在配置文件中编写的这类信息有哪些呢？在 .NET 4 中，您甚至可以决定完全不使用配置文件。  
  
-   现有的一组 WCF 服务难以进行配置和维护。配置文件具有数千行 XML 代码，操作这些代码会产生很大的风险。需要获得帮助以减少代码量，来提高可管理性。  
  
## 数据协定解析程序  
 .NET 3.5 中包含对已知类型的设计的几个限制：  
  
-   在序列化或反序列化过程中不能动态添加已知类型。  
  
-   序列化程序无法处理未知的 xsi:type 信息。  
  
-   用户无法指定他们想要在网络上显示的 xsi:type，例如，使网络上的序列化实例更小一些。  
  
 [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md) 在 .NET 4.5 中解决了这些问题。  
  
### 入门  
  
-   [数据协定解析程序 API 文档](http://go.microsoft.com/fwlink/?LinkId=204946)  
  
-   [引入数据协定解析程序](http://go.microsoft.com/fwlink/?LinkId=204947)  
  
-   示例：  
  
    -   [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md)  
  
    -   [KnownAssemblyAttribute](../../../docs/framework/wcf/samples/knownassemblyattribute.md)  
  
### 数据协定解析程序方案  
  
-   无需在服务中声明数十个 <xref:System.Runtime.Serialization.KnownTypeAttribute> 对象。  
  
-   减小 XML Blob 的大小。  
  
## 流程图  
 流程图是用于以可视方式表示域问题的已知范例。它是我们在 .NET 4 中引入的新控制流样式。流程图的核心特点是，在任何给定时间只能执行一个活动。流程图可以表示循环和备选结果，但无法表示多个节点的并发执行。  
  
### 入门  
  
-   在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。在工作流设计器中添加流程图。  
  
-   流程图功能使用以下类：  
  
    -   <xref:System.Activities.Statements.Flowchart>  
  
    -   <xref:System.Activities.Statements.FlowNode>  
  
    -   <xref:System.Activities.Statements.FlowDecision>  
  
    -   <xref:System.Activities.Statements.FlowStep>  
  
    -   <xref:System.Activities.Statements.FlowSwitch%601>  
  
-   示例：  
  
    -   [使用 TryCatch 在 Flowchart 活动中进行错误处理](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    -   [使用 FlowChart 与 Pick 的组合的 StateMachine 方案](../../../docs/framework/windows-workflow-foundation/samples/statemachine-scenario-using-a-combination-of-flowchart-and-pick.md)  
  
    -   [招聘流程](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
-   设计器文档：  
  
    -   [流程图活动设计器](../Topic/Flowchart%20Activity%20Designers.md)  
  
### 流程图方案  
 流程图活动可用于实现猜谜游戏。猜谜游戏非常简单：计算机选择一个随机数，然后玩家必须猜出该数字。当玩家提交所猜的每个数字时，计算机会给出一个提示（即"试试较小的数字"）。如果玩家在 7 次之内猜出该数字，则计算机将为其显示特定的祝贺语。可使用以下过程活动组合来实现此游戏：  
  
-   <xref:System.Activities.Statements.Sequence>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.TryCatch>  
  
-   <xref:System.Activities.Statements.Assign%601>  
  
-   <xref:System.Activities.Statements.If>  
  
## 过程活动（Sequence、If、ForEach、Switch、Assign、DoWhile 和 While）  
 过程活动提供了一种机制，该机制使用程序员熟悉的概念为顺序控制流建模。这些活动会启用传统结构化编程语言构造，并在适当时提供采用公共过程语言（如 C\#\/VB）的语言奇偶校验。  
  
### 入门  
  
-   在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。在工作流设计器中添加过程活动。  
  
-   示例：  
  
    -   [招聘流程](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
    -   [企业采购过程](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)  
  
-   设计器文档：  
  
    -   [Parallel 活动设计器](../Topic/Parallel%20Activity%20Designer.md)  
  
    -   [ParallelForEach\<T\> 活动设计器](../Topic/ParallelForEach%3CT%3E%20Activity%20Designer.md)  
  
### 过程活动方案  
  
-   <xref:System.Activities.Statements.Parallel>并行：具有文档审批工作流的 Intranet 文档管理系统。文档需要先经过多个部门人员的审批，然后才能发布到 Intranet。尚未建立审批顺序；它们会在文档处于“审批挂起”阶段时随时出现。当用户提交文档以供审阅时，该文档必须先由用户的直属经理、Intranet 管理员和内部通信经理审批。  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>：WF 应用程序将管理大型公司内的公司采购。公司规则指明，在计划任何采购操作前需要评估三个不同的供应商。采购部员工将从公司的供应商列表中选择三个供应商。在选择这些供应商并向他们发送通知后，公司将等待他们提出经济实惠的建议。这些建议会以任意顺序出现。为了在 WF 中实现此方案，我们使用了 <xref:System.Activities.Statements.ParallelForEach%601>，它会循环访问供应商集合并要求他们提供经济建议。收集完所有建议后，选择并显示最好的建议。  
  
## InvokeMethod  
 <xref:System.Activities.Statements.InvokeMethod> 活动允许在范围内的对象或类型中调用公共方法。它支持调用实例和带有或不带参数（包括参数数组）的静态方法以及泛型方法。它还允许以同步方式和异步方式执行方法。  
  
### 入门  
  
-   在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。在工作流设计器中添加一个 <xref:System.Activities.Statements.InvokeMethod> 活动，并对该活动配置静态和实例方法。  
  
-   示例：  
  
    -   [InvokeMethod](../../../docs/framework/windows-workflow-foundation/samples/invokemethod.md)  
  
-   设计器文档：[InvokeMethod 活动设计器](../Topic/InvokeMethod%20Activity%20Designer.md)  
  
### InvokeMethod 方案  
  
-   需要调用范围内的对象中的方法。例如，需要将值添加到词典。调用词典实例的 Add 方法并提供键和值。  
  
-   需要对旧 CLR 对象调用方法。如果旧类在工作流执行过程中位于范围内，则可以使用 <xref:System.Activities.Statements.InvokeMethod>，而不是创建将包装对该旧类的调用的自定义活动。  
  
## 错误处理活动  
 <xref:System.Activities.Statements.TryCatch> 活动提供了一种机制，用于捕获在执行一组包含的活动的过程中发生的异常（类似于 C\#\/VB 中的 Try\/Catch 构造）。<xref:System.Activities.Statements.TryCatch> 提供了在工作流级别的异常处理。在引发未处理的异常时，系统将终止工作流，并且不会执行 Finally 块。此行为与 C\# 一致。  
  
### 入门  
  
-   在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。在工作流设计器中添加 <xref:System.Activities.Statements.TryCatch> 活动。  
  
-   示例：  
  
    1.  [使用 TryCatch 在 Flowchart 活动中进行错误处理](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    2.  [使用过程性活动](../../../docs/framework/windows-workflow-foundation/samples/using-procedural-activities.md)  
  
-   设计器文档：[错误处理活动设计器](../Topic/Error%20Handling%20Activity%20Designers.md)  
  
### 错误处理方案  
 需要执行一组活动，并且需要在发生错误时执行特定的逻辑。如果在执行错误处理逻辑的过程中发现该错误是不可恢复的，则会重新引发该异常，并且父活动（或主机）将处理该问题。  
  
## Pick 活动  
 <xref:System.Activities.Statements.Pick> 活动提供基于事件 WF 的控制流建模。<xref:System.Activities.Statements.Pick> 包含许多分支，每个分支都要等待特定事件发生后才运行。在此设置中，<xref:System.Activities.Statements.Pick> 的行为类似于 <xref:System.Activities.Statements.Switch%601>，该活动将只对其执行正在侦听的一组事件中的某个事件。每个分支都是事件驱动的，并且发生的事件将先运行对应的分支。所有其他分支会取消并停止侦听事件。  
  
### 入门  
  
-   在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。在工作流设计器中添加 <xref:System.Activities.Statements.Pick> 活动。  
  
-   示例：[使用 Pick 活动](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)  
  
-   设计器文档：[Pick 活动设计器](../Topic/Pick%20Activity%20Designer.md)  
  
### Pick 方案  
 系统需要提示用户进行输入。在正常情况下，开发人员将使用类似于 <xref:System.Console.ReadLine%2A> 这样的方法调用来提示用户进行输入。此设置的问题是，程序会一直等到用户输入后才运行。在此方案中，需要超时来取消对阻止活动的阻止。常见的方案会要求在给定持续时间内完成任务。在阻止活动超时的方案中，Pick 将添加大量值。  
  
## WCF 路由服务  
 路由服务设计为一种泛型软件路由器，可利用它控制 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 消息在客户端和服务之间流动的方式。路由服务允许您将客户端与服务分离，从而使您在可支持的配置方面拥有更大的自由度，并可灵活考虑承载服务的方式。在 .NET 3.5 中，客户端和服务是紧密耦合的；客户端必须了解需要进行通信的所有服务以及这些服务的位置。此外，.Net Framework 3.5 中的 WCF 具有以下限制：  
  
-   错误处理较为复杂，因为必须将此逻辑硬编码到客户端中。  
  
-   客户端和服务必须始终使用同一绑定。  
  
-   服务很少能适当地分解：让客户端与一个能实现所有操作的服务进行通信而不必在多个服务之间选择，这样的做法更简单一些。  
  
 .Net 4 中的路由服务旨在更轻松地处理这些问题。新的路由服务具有以下功能：  
  
1.  基于内容的路由（<xref:System.ServiceModel.Dispatcher.MessageFilter> 对象会检查消息以确定其发送位置。）  
  
2.  协议桥接（传输和消息）  
  
3.  错误处理（路由器将捕获通信异常并将故障转移到备份终结点）  
  
4.  <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> 和路由配置的动态（内存中）更新。  
  
### 入门  
  
1.  文档：[路由](../../../docs/framework/wcf/feature-details/routing.md)  
  
2.  示例：[路由服务 &#91;WCF 示例&#93;](../../../docs/framework/wcf/samples/routing-services.md)  
  
3.  博客：[路由规则！](http://go.microsoft.com/fwlink/?LinkId=204956)  
  
### 路由方案  
 路由服务在以下方案中很有用：  
  
-   客户端可与多个服务通信，而无需直接处理所有这些服务。  
  
-   客户端可对客户端请求执行其他逻辑以确定其路由位置  
  
-   将客户端执行的操作分解为多个服务实现而不重构客户端。  
  
-   客户端和服务可与具有不同安全设置的不同绑定进行通信。  
  
-   可以使客户端更为可靠一些，从而防止出现故障或服务不可用的情况。  
  
## WCF Discovery  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Discovery 是一种框架技术，允许您将发现机制并入应用程序基础结构中。利用此技术，您可以使服务可发现，并配置客户端以搜索服务。不再需要使用终结点对客户端进行硬编码，即可使应用程序的可靠性更高，容错能力更强。Discovery 是一个用于将自动配置功能构建到应用程序中的最佳平台。  
  
 该产品是基于 WS\-Discovery 标准构建的。它设计为具有互操作性、可扩展性和通用性。该产品支持两种操作模式：  
  
1.  托管：在此模式中，网络上有一个了解现有服务的实体，客户端可直接从该实体查询信息。这与 Active Directory 类似。  
  
2.  临时：在此模式中，客户端使用多播消息来查找服务。  
  
 此外，发现消息是网络协议不可知的；可以对支持该模式要求的任何协议使用它们。例如，发现多播消息可通过 UDP 通道或支持多播消息传递的任何其他网络发送。这些设计点融入了功能灵活性，允许您将发现专用于您的解决方案。  
  
### 入门  
  
-   文档：[WCF Discovery](../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
  
-   示例：[发现（示例）](../../../docs/framework/wcf/samples/discovery-samples.md)  
  
### Discovery 方案  
 开发人员不希望对终结点进行硬编码，因为我的服务的可用时间未知。相反，开发人员希望在运行时选择服务。应用程序的各个组件之间需要更大程度的分离、稳定性和自动配置。  
  
## 跟踪  
 工作流跟踪有助于详细了解工作流实例的执行。跟踪事件将在工作流中的活动执行时在工作流实例级别从工作流发出。需要将工作流跟踪参与者添加到工作流主机中以订阅跟踪记录。使用跟踪配置文件筛选跟踪记录。.NET Framework 提供了 ETW（Windows 事件跟踪）跟踪参与者，并在 machine.config 文件中安装了基本配置文件。  
  
### 入门  
  
1.  在 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 中，创建一个 WCF 工作流服务应用程序项目。<xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 对将置于画布上以开始操作。  
  
2.  打开 web.config 并添加一个无配置文件的 ETW 跟踪行为。  
  
    1.  使用默认配置文件。  
  
    2.  打开事件查看器并启用以下节点中的分析通道：**“事件查看器”**、**“应用程序和服务日志”**、**“Microsoft”**、**“Windows”**和**“应用程序服务器\-应用程序”**。右击**“分析”**，然后选择**“启用日志”**。  
  
    3.  运行工作流服务。  
  
    4.  在事件查看器中观察工作流跟踪事件。  
  
3.  示例：[跟踪](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)  
  
4.  概念文档：[工作流跟踪](../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)。  
  
## SQL 工作流实例存储  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 是实例存储的基于 SQL Server 的实现。实例存储将存储正在运行的实例的状态以及加载和恢复该实例所需的所有数据。服务主机将在工作流仍存在时指示实例存储保存实例状态，并在该实例的消息到达或延迟活动过期时指示实例存储加载实例状态。  
  
### 入门  
  
1.  在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个包含隐式或显式 <xref:System.Activities.Statements.Persist> 活动的工作流。将 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 行为添加到工作流服务主机。这可以在代码或应用程序配置文件中完成。  
  
2.  示例：[持久性](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)  
  
3.  概念文档：[SQL 工作流实例存储](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)。