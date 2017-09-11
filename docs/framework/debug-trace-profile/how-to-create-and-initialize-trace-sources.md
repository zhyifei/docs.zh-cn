---
title: "如何：创建和初始化跟踪源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- trace sources
- initializing trace sources
- configuration files [.NET Framework], trace sources
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
caps.latest.revision: 10
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1df5f06afaf23795a0efd6af763e29193ba82d90
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-create-and-initialize-trace-sources"></a><span data-ttu-id="09940-102">如何：创建和初始化跟踪源</span><span class="sxs-lookup"><span data-stu-id="09940-102">How to: Create and Initialize Trace Sources</span></span>
<span data-ttu-id="09940-103"><xref:System.Diagnostics.TraceSource> 类由应用程序用来生成可与应用程序相关联的跟踪。</span><span class="sxs-lookup"><span data-stu-id="09940-103">The <xref:System.Diagnostics.TraceSource> class is used by applications to produce traces that can be associated with the application.</span></span> <span data-ttu-id="09940-104"><xref:System.Diagnostics.TraceSource> 提供了一些跟踪方法，利用这些跟踪方法，你可以方便地跟踪事件，跟踪数据和发出信息跟踪。</span><span class="sxs-lookup"><span data-stu-id="09940-104"><xref:System.Diagnostics.TraceSource> provides tracing methods that allow you to easily trace events, trace data, and issue informational traces.</span></span> <span data-ttu-id="09940-105">你可以使用或不使用配置文件来创建和初始化 <xref:System.Diagnostics.TraceSource> 的跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="09940-105">Trace output from <xref:System.Diagnostics.TraceSource> can be created and initialized with or without the use of configuration files.</span></span> <span data-ttu-id="09940-106">本主题提供这两种选项的说明。</span><span class="sxs-lookup"><span data-stu-id="09940-106">This topic provides instructions for both options.</span></span> <span data-ttu-id="09940-107">但是，建议你使用配置文件，以便于重新配置在运行时由跟踪源生成的跟踪。</span><span class="sxs-lookup"><span data-stu-id="09940-107">However, we recommend that you use configuration files to facilitate the reconfiguration of the traces produced by trace sources at run time.</span></span>  
  
### <a name="to-create-and-initialize-a-trace-source-using-a-configuration-file"></a><span data-ttu-id="09940-108">使用配置文件创建和初始化跟踪源</span><span class="sxs-lookup"><span data-stu-id="09940-108">To create and initialize a trace source using a configuration file</span></span>  
  
1.  <span data-ttu-id="09940-109">创建 Visual Studio 控制台应用程序项目，然后使用以下代码替换提供的代码。</span><span class="sxs-lookup"><span data-stu-id="09940-109">Create a Visual Studio console application project and replace the supplied code with the following code.</span></span> <span data-ttu-id="09940-110">此代码将记录错误和警告，并将其中一些输出到控制台，将其中一些输出到由配置文件中的各个项创建的 myListener 文件。</span><span class="sxs-lookup"><span data-stu-id="09940-110">This code logs errors and warnings and outputs some of them to the console, and some of them to the myListener file that is created by the entries in the configuration file.</span></span>  
  
     <span data-ttu-id="09940-111">[!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]  [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="09940-111">[!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]  [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]</span></span>  
  
2.  <span data-ttu-id="09940-112">向项目添加一个应用程序配置文件（如果没有），以初始化步骤 1 代码示例中名为 `TraceSourceApp` 的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="09940-112">Add an application configuration file, if one is not present, to the project to initialize the trace source named `TraceSourceApp` in the code example in step 1.</span></span>  
  
3.  <span data-ttu-id="09940-113">将默认配置文件内容替换为以下设置，以便为步骤 1 中创建的跟踪源初始化控制台跟踪侦听器和文本编写器跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="09940-113">Replace the default configuration file content with the following settings to initialize a console trace listener and a text writer trace listener for the trace source that was created in step 1.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"   
            switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"   
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"   
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"   
            type="System.Diagnostics.TextWriterTraceListener"   
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
     <span data-ttu-id="09940-114">除配置跟踪侦听器外，配置文件还同时为这两个侦听器创建筛选器，并为跟踪源创建一个源开关。</span><span class="sxs-lookup"><span data-stu-id="09940-114">In addition to configuring the trace listeners, the configuration file creates filters for both listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="09940-115">其中演示了两种添加跟踪侦听器的技术：将侦听器直接添加到跟踪源，以及将侦听器添加到共享的侦听器集合，然后按名称将它添加到跟踪源。</span><span class="sxs-lookup"><span data-stu-id="09940-115">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="09940-116">为这两个侦听器标识的筛选器用不同的源级别进行初始化。</span><span class="sxs-lookup"><span data-stu-id="09940-116">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="09940-117">这样导致某些消息仅由其中一个侦听器编写。</span><span class="sxs-lookup"><span data-stu-id="09940-117">This results in some messages being written by only one of the two listeners.</span></span>  
  
     <span data-ttu-id="09940-118">配置文件在初始化应用程序时初始化跟踪源的设置。</span><span class="sxs-lookup"><span data-stu-id="09940-118">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="09940-119">应用程序可以动态更改配置文件设置的属性，以重写用户指定的任何设置。</span><span class="sxs-lookup"><span data-stu-id="09940-119">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span> <span data-ttu-id="09940-120">例如，你可能想要确保始终将关键消息发送到文本文件，而不管当前配置设置如何。</span><span class="sxs-lookup"><span data-stu-id="09940-120">For example, you might want to ensure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span> <span data-ttu-id="09940-121">示例代码演示如何重写配置文件设置以确保将关键消息输出到跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="09940-121">The example code demonstrates how to override configuration file settings to ensure that critical messages are output to the trace listeners.</span></span>  
  
     <span data-ttu-id="09940-122">在应用程序执行时更改配置文件设置不会更改初始设置。</span><span class="sxs-lookup"><span data-stu-id="09940-122">Changing the configuration file settings while the application is executing does not change the initial settings.</span></span> <span data-ttu-id="09940-123">若要更改设置，必须重新启动应用程序或使用 <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName> 方法以编程方式刷新应用程序。</span><span class="sxs-lookup"><span data-stu-id="09940-123">To change the settings, you must either restart the application or programmatically refresh the application by using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName> method.</span></span>  
  
### <a name="to-initialize-trace-sources-listeners-and-filters-without-a-configuration-file"></a><span data-ttu-id="09940-124">不使用配置文件初始化跟踪源、侦听器和筛选器</span><span class="sxs-lookup"><span data-stu-id="09940-124">To initialize trace sources, listeners, and filters without a configuration file</span></span>  
  
-   <span data-ttu-id="09940-125">使用以下示例代码在不使用配置文件的情况下通过跟踪源启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="09940-125">Use the following example code to enable tracing through a trace source without using a configuration file.</span></span> <span data-ttu-id="09940-126">这不是建议的做法，但在某此情况下，你可能不想依赖配置文件来确保跟踪。</span><span class="sxs-lookup"><span data-stu-id="09940-126">This is not a recommended practice, but there may be circumstances in which you do not want to depend on configuration files to ensure tracing.</span></span>  
  
     <span data-ttu-id="09940-127">[!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]  [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="09940-127">[!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]  [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09940-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09940-128">See Also</span></span>  
 <span data-ttu-id="09940-129"><xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="09940-129"><xref:System.Diagnostics.TraceSource></span></span>   
 <span data-ttu-id="09940-130"><xref:System.Diagnostics.TextWriterTraceListener></span><span class="sxs-lookup"><span data-stu-id="09940-130"><xref:System.Diagnostics.TextWriterTraceListener></span></span>   
 <span data-ttu-id="09940-131"><xref:System.Diagnostics.ConsoleTraceListener></span><span class="sxs-lookup"><span data-stu-id="09940-131"><xref:System.Diagnostics.ConsoleTraceListener></span></span>   
 <span data-ttu-id="09940-132"><xref:System.Diagnostics.EventTypeFilter></span><span class="sxs-lookup"><span data-stu-id="09940-132"><xref:System.Diagnostics.EventTypeFilter></span></span>   
 [<span data-ttu-id="09940-133">跟踪应用程序和在应用程序中插入检测点</span><span class="sxs-lookup"><span data-stu-id="09940-133">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)

