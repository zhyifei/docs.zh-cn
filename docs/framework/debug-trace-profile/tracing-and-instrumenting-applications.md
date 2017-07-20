---
title: "跟踪应用程序和在应用程序中插入检测点 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "跟踪 [.NET Framework]"
  - "调试 [.NET Framework]、 检测"
  - "性能监视设备"
  - "检测，关于规范"
  - "有关跟踪的跟踪 [.NET Framework]"
  - "性能监视跟踪代码"
  - "Trace 类，.NET 应用程序的规范"
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
caps.latest.revision: 21
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 21
---
# 跟踪应用程序和在应用程序中插入检测点
跟踪是指应用程序正在运行时监视其执行情况的方式。 可在开发 .NET Framework 应用程序时向其添加跟踪和调试检测，也可在开发应用程序时或在部署此应用程序之后使用此检测。 您可以使用<xref:System.Diagnostics.Trace?displayProperty=fullName>， <xref:System.Diagnostics.Debug?displayProperty=fullName>，和<xref:System.Diagnostics.TraceSource?displayProperty=fullName>来记录有关错误和应用程序执行在日志、 文本文件或其他设备以供日后分析信息的类。  
  
 术语*instrumentation*指监视或测量产品的性能级别和诊断错误的功能。 在编程中，即指应用程序合并以下功能的能力：  
  
-   **代码跟踪**-接收有关应用程序在运行时执行的信息性消息。  
  
-   **调试**-跟踪并修复正在开发的应用程序中的编程错误。 有关详细信息，请参阅[调试](../Topic/Debugging%20in%20Visual%20Studio.md)。  
  
-   **性能计数器**-使您能够跟踪您的应用程序的性能的组件。 有关详细信息，请参阅[性能计数器](../../../docs/framework/debug-trace-profile/performance-counters.md)。  
  
-   **事件日志**-可让你组件接收和跟踪应用程序的执行过程中重要事件。 有关详细信息，请参阅<xref:System.Diagnostics.EventLog>类。  
  
 通过将跟踪语句置于代码中的关键位置来检测应用程序非常适合分布式应用程序。 通过使用跟踪语句，可检测应用程序，从而在出现故障时显示相关信息并监视应用程序的运行情况。  
  
 <xref:System.Diagnostics.TraceSource>类提供了增强的跟踪功能，可用来代替较旧的静态方法<xref:System.Diagnostics.Trace>和<xref:System.Diagnostics.Debug>跟踪类。 熟悉<xref:System.Diagnostics.Trace>和<xref:System.Diagnostics.Debug>仍然使用广泛使用的类，但<xref:System.Diagnostics.TraceSource>类建议对新的跟踪命令，如<xref:System.Diagnostics.TraceSource.TraceEvent%2A>和<xref:System.Diagnostics.TraceSource.TraceData%2A>。  
  
 <xref:System.Diagnostics.Trace>和<xref:System.Diagnostics.Debug>类是基本相同，但该过程和函数的<xref:System.Diagnostics.Trace>类默认编译为发布版本，而那些<xref:System.Diagnostics.Debug>类的并非如此。  
  
 <xref:System.Diagnostics.Trace>和<xref:System.Diagnostics.Debug>类提供了用来监视和检查在开发期间或部署后的应用程序性能。 例如，您可以使用<xref:System.Diagnostics.Trace>类，以跟踪特定类型的已部署的应用程序中的操作发生 （例如新建数据库连接），因而可以监视应用程序的效率。  
  
## <a name="code-tracing-and-debugging"></a>代码跟踪和调试  
 在开发期间，您可以使用的输出方法<xref:System.Diagnostics.Debug>类在 Visual Studio 集成的开发环境 (IDE) 的输出窗口中显示消息。 例如:   
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
  
```  
  
 上述每个示例将显示"Hello World ！" 在输出窗口时在调试器中运行该应用程序中。  
  
 由此，你可以根据应用程序在测试环境中的行为对它进行调试并优化其性能。 您可以在调试版本中调试您的应用程序<xref:System.Diagnostics.Debug>启用状态，以便接收所有调试输出的条件属性。 准备好发布应用程序时，您可以在关闭情况下编译您的发布版本<xref:System.Diagnostics.Debug>条件特性，因此编译器不会在最终可执行文件中包含调试代码。 有关详细信息，请参阅[如何︰ 使用跟踪和调试进行条件编译](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)。 您的应用程序的不同生成配置的详细信息，请参阅[编译和生成](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)。  
  
 您也可以跟踪代码执行的已安装的应用程序，使用方法<xref:System.Diagnostics.Trace>类。 通过将[跟踪开关](../../../docs/framework/debug-trace-profile/trace-switches.md)在代码中，您可以控制是否执行跟踪以及它是广泛程度。 这使你可以监视应用程序在生产环境中的状态。 对使用在多台计算机上运行的多个组件的业务应用程序而言，这一点尤其重要。 可通过配置文件控制如何在部署后使用开关。 有关详细信息，请参阅[如何︰ 创建、 初始化和配置跟踪开关](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)。  
  
 开发要对其使用跟踪的应用程序时，应用程序代码中通常要包含跟踪和调试消息。 在准备好部署应用程序时，您可以在关闭情况下编译您的发布版本**调试**条件属性。 不过，您可以打开**跟踪**条件属性，以便编译器将跟踪代码包括可执行文件中。 有关详细信息，请参阅[如何︰ 使用跟踪和调试进行条件编译](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)。  
  
### <a name="phases-of-code-tracing"></a>代码跟踪的阶段  
 代码跟踪有&3; 个阶段：  
  
1.  **检测**— 将跟踪代码添加到您的应用程序。  
  
2.  **跟踪**— 跟踪代码向指定目标写入信息。  
  
3.  **分析**— 评估跟踪信息，以确定和了解应用程序中的问题。  
  
 开发过程中，所有调试和跟踪输出方法都默认将信息写入 Visual Studio 的输出窗口。 在已部署的应用程序中，方法将跟踪信息写入所指定的目标。 指定的输出目标的跟踪或调试的详细信息，请参阅[跟踪侦听器](../../../docs/framework/debug-trace-profile/trace-listeners.md)。  
  
 以下内容概述了使用跟踪来分析和更正已部署的应用程序中的潜在问题时通常涉及的主要步骤。 有关如何执行这些步骤的详细信息，请参阅相应链接。  
  
##### <a name="to-use-tracing-in-an-application"></a>若要在应用程序中使用跟踪  
  
1.  请思考部署应用程序后想要现场接收哪种跟踪输出。  
  
2.  创建一组开关。 有关详细信息，请参阅[如何︰ 配置跟踪开关](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)。  
  
3.  向应用程序代码添加跟踪语句。  
  
4.  确定要显示跟踪输出的位置并添加相应的侦听器。 有关详细信息，请参阅[创建和初始化跟踪侦听器](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md)。  
  
5.  测试和调试应用程序及其包含的跟踪代码。  
  
6.  使用下面一个过程将应用程序编译为可执行代码：  
  
    -   使用**生成**菜单以及**调试**页**属性页**中对话框**解决方案资源管理器**。 在 Visual Studio 中编译时，请使用此选项。  
  
         \- 或 -  
  
    -   使用**跟踪**和**调试**编译的命令行方法的编译器指令。 有关详细信息，请参阅[使用跟踪和调试进行条件编译](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)。 从命令行进行编译时，请使用此选项。  
  
7.  如果在运行时出现问题，请打开相应的跟踪开关。 有关详细信息，请参阅[配置跟踪开关](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)。  
  
     跟踪代码向指定目标写入跟踪消息，如屏幕、文本文件或事件日志。 中附带的侦听器类型**Trace.Listeners**集合确定目标。  
  
8.  分析跟踪消息以确定和了解应用程序中的问题。  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>跟踪检测和分布式应用程序  
 在创建分布式应用程序时，可能难以按要使用的方式测试应用程序。 开发团队几乎都不能测试操作系统或 Web 浏览器（包括所有本地化的语言选项）的所有潜在组合，也不能模拟将同时访问应用程序的大量用户。 在这些情况下，无法测试分布式应用程序将如何响应高容量、不同的设置和最终用户的唯一行为。 此外，分布式应用程序的很多部件都不具有可直接与之交互或可用于查看这些部件的行为的用户界面。  
  
 但是，您可以弥补这个使分布式应用程序以描述系统管理员，尤其是存在错误时，通过感兴趣的某些事件*检测*应用程序 — 也就是说，将跟踪语句置于代码中的关键位置。 由此，如果运行时发生意外事件（例如，响应时间过于缓慢），就可确定可能的原因。  
  
 借助跟踪语句，可避免执行以下艰难任务：检查原始源代码、对其进行修改、重新编译以及试图在调试环境中生成运行时错误。 请记住，检测应用程序这一操作可用于显示错误以及监视性能。  
  
## <a name="strategic-placement-of-trace-statements"></a>将跟踪语句置于关键位置  
 放置供运行时期间使用的跟踪语句时，必须特别小心。 注意考虑部署的应用程序中可能需要什么跟踪信息，以便充分涵盖所有可能的跟踪方案。 然而，使用跟踪的应用程序差别很大，因此关于将跟踪置于关键位置，没有通用准则。 有关放置跟踪语句的详细信息，请参阅[如何︰ 向应用程序代码添加跟踪语句](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)。  
  
## <a name="output-from-tracing"></a>跟踪的输出  
 跟踪输出由名的对象来收集*侦听器*。 侦听器是接收跟踪输出，并将它写入输出设备（通常为窗口、日志或文本文件）的对象。 创建一个跟踪侦听器时，通常会被添加到<xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName>集合中，这样侦听器就可以接收所有跟踪输出。  
  
 跟踪信息始终被写入在至少到默认<xref:System.Diagnostics.Trace>输出目标<xref:System.Diagnostics.DefaultTraceListener>。 如果由于某种原因删除了<xref:System.Diagnostics.DefaultTraceListener>而无需添加到任何其他侦听器<xref:System.Diagnostics.Trace.Listeners%2A>集合中，您将不会收到任何跟踪消息。 有关详细信息，请参阅[跟踪侦听器](../../../docs/framework/debug-trace-profile/trace-listeners.md)。  
  
 六个<xref:System.Diagnostics.Debug>成员和<xref:System.Diagnostics.Trace>下表中列出了写入跟踪信息的方法。  
  
|方法|输出|  
|------------|------------|  
|**断言**|指定的文本；若未指定，则为调用堆栈。 将输出写入只作为中的参数如果指定的条件**Assert**语句是**false**。|  
|**失败**|指定的文本；若未指定，则为调用堆栈。|  
|**写入**|指定的文本。|  
|**WriteIf**|如果指定的文本，作为中的参数指定的条件**WriteIf**满足语句。|  
|**WriteLine**|指定的文本和一个回车符。|  
|**WriteLineIf**|返回指定的文本和一个回车符，如果作为中的参数指定的条件**WriteLineIf**满足语句。|  
  
 中的所有侦听器<xref:System.Diagnostics.Trace.Listeners%2A>集合接收到上表中所述的消息，但所执行的操作可能因何种侦听器接收的消息。 例如， <xref:System.Diagnostics.DefaultTraceListener>显示一个断言对话框，在接收时**失败**与否**Assert**通知，但<xref:System.Diagnostics.TextWriterTraceListener>只是将输出写入它的流。  
  
 可通过实现自己的侦听器生成自定义结果。 例如，自定义跟踪侦听器可能将消息显示给消息框，或连接到数据库以将消息添加到表中。 所有自定义侦听器都应支持上述&6; 种方法。 有关创建开发人员定义的侦听器的详细信息，请参阅<xref:System.Diagnostics.TraceListener> .NET Framework 引用中。  
  
> [!NOTE]
>  在[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]、 **Debug.Write**， **Debug.WriteIf**， **Debug.WriteLine**，和**Debug.WriteLineIf**方法已代替**Debug.Print**在早期版本的 Visual Basic 中可用的方法。  
  
 **编写**和**WriteLine**方法始终写入的文本，您指定。 **Assert**， **WriteIf**，和**WriteLineIf**需要布尔型参数，用于控制它们是否写入指定的文本; 他们编写指定的文本表达式是否**true** (对于**WriteIf**和**WriteLineIf**)，或**false** (对于**Assert**)。 **失败**方法始终写入指定的文本。 有关详细信息，请参阅[如何︰ 向应用程序代码添加跟踪语句](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)和.NET Framework 参考。  
  
## <a name="security-concerns"></a>安全问题  
 如果在部署 ASP.NET 应用程序之前未禁用跟踪和调试，你的应用程序可能会泄漏自身的相关信息，从而被恶意程序利用。 有关详细信息，请参阅[如何︰ 使用跟踪和调试进行条件编译](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)，[编译和生成](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)，和[如何︰ 创建、 初始化和配置跟踪开关](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)。 也可通过 Internet 信息服务 (IIS) 配置调试。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 [代码约定](../../../docs/framework/debug-trace-profile/code-contracts.md)   
 [C#、 F # 和 Visual Basic 项目类型](../Topic/Debugging%20Preparation:%20C%23,%20F%23,%20and%20Visual%20Basic%20Project%20Types.md)   
 [如何︰ 向应用程序代码添加跟踪语句](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [如何︰ 使用跟踪和调试进行条件编译](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)   
 [如何︰ 创建、 初始化和配置跟踪开关](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [如何︰ 创建和初始化跟踪源](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [如何︰ 将 TraceSource 和筛选器，用于跟踪侦听器](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)   
 [跟踪侦听器](../../../docs/framework/debug-trace-profile/trace-listeners.md)   
 [跟踪开关](../../../docs/framework/debug-trace-profile/trace-switches.md)