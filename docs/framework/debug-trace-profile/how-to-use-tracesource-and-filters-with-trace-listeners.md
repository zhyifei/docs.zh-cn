---
title: 如何：使用 TraceSource 和筛选器与跟踪侦听器
ms.date: 03/30/2017
helpviewer_keywords:
- initializing trace listeners
- configuration files [.NET Framework], trace listeners
- app.config files, trace listeners
- levels of writing trace messages
- trace listeners, TraceSource class
- application configuration files, trace listeners
- filters, trace listeners
- TraceSource class, trace listeners
- trace listeners, creating
- trace listeners, filters
- trace listeners, initializing
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc81e1e13f942f5db4fec5cc607264d499b63629
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146074"
---
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a><span data-ttu-id="95dc2-102">如何：使用 TraceSource 和筛选器与跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="95dc2-102">How to: Use TraceSource and Filters with Trace Listeners</span></span>
<span data-ttu-id="95dc2-103">.NET Framework 版本 2.0 的新功能之一是增强型的跟踪系统。</span><span class="sxs-lookup"><span data-stu-id="95dc2-103">One of the new features in the .NET Framework version 2.0 is an enhanced tracing system.</span></span> <span data-ttu-id="95dc2-104">基本前提不变：跟踪消息通过交换机发送到侦听器，侦听器将数据报告给相关联的输出介质。</span><span class="sxs-lookup"><span data-stu-id="95dc2-104">The basic premise is unchanged: tracing messages are sent through switches to listeners, which report the data to an associated output medium.</span></span> <span data-ttu-id="95dc2-105">2.0 版的主要区别是，可以通过 <xref:System.Diagnostics.TraceSource> 类的实例启动跟踪。</span><span class="sxs-lookup"><span data-stu-id="95dc2-105">A primary difference for version 2.0 is that traces can be initiated through instances of the <xref:System.Diagnostics.TraceSource> class.</span></span> <span data-ttu-id="95dc2-106"><xref:System.Diagnostics.TraceSource> 用作增强型跟踪系统，并可用来代替较旧的 <xref:System.Diagnostics.Trace> 和 <xref:System.Diagnostics.Debug> 跟踪类的静态方法。</span><span class="sxs-lookup"><span data-stu-id="95dc2-106"><xref:System.Diagnostics.TraceSource> is intended to function as an enhanced tracing system and can be used in place of the static methods of the older <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> tracing classes.</span></span> <span data-ttu-id="95dc2-107">熟悉的 <xref:System.Diagnostics.Trace> 和 <xref:System.Diagnostics.Debug> 类仍存在，但建议使用 <xref:System.Diagnostics.TraceSource> 类进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="95dc2-107">The familiar <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> classes still exist, but the recommended practice is to use the <xref:System.Diagnostics.TraceSource> class for tracing.</span></span>  
  
 <span data-ttu-id="95dc2-108">本主题描述如何将 <xref:System.Diagnostics.TraceSource> 与应用程序配置文件结合使用。</span><span class="sxs-lookup"><span data-stu-id="95dc2-108">This topic describes the use of a <xref:System.Diagnostics.TraceSource> coupled with an application configuration file.</span></span>  <span data-ttu-id="95dc2-109">可在不使用配置文件的情况下使用 <xref:System.Diagnostics.TraceSource> 进行跟踪，但是不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="95dc2-109">It is possible, although not recommended, to trace using a <xref:System.Diagnostics.TraceSource> without the use of a configuration file.</span></span> <span data-ttu-id="95dc2-110">无需配置文件的跟踪信息，请参阅[如何：创建和初始化跟踪源](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)。</span><span class="sxs-lookup"><span data-stu-id="95dc2-110">For information on tracing without a configuration file, see [How to: Create and Initialize Trace Sources](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md).</span></span>  
  
### <a name="to-create-and-initialize-your-trace-source"></a><span data-ttu-id="95dc2-111">创建和初始化跟踪源</span><span class="sxs-lookup"><span data-stu-id="95dc2-111">To create and initialize your trace source</span></span>  
  
1.  <span data-ttu-id="95dc2-112">使用跟踪检测应用程序的第一步是创建跟踪源。</span><span class="sxs-lookup"><span data-stu-id="95dc2-112">The first step to instrumenting an application with tracing is to create a trace source.</span></span> <span data-ttu-id="95dc2-113">在含有各种组件的大型项目中，可以为每个组件创建一个单独的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="95dc2-113">In large projects with various components, you can create a separate trace source for each component.</span></span> <span data-ttu-id="95dc2-114">建议将应用程序名称作为跟踪源名称。</span><span class="sxs-lookup"><span data-stu-id="95dc2-114">The recommended practice is to use the application name for the trace source name.</span></span> <span data-ttu-id="95dc2-115">这会使不同的跟踪更容易保持独立。</span><span class="sxs-lookup"><span data-stu-id="95dc2-115">This will make it easier to keep the different traces separate.</span></span> <span data-ttu-id="95dc2-116">以下代码创建一个新的跟踪源 (`mySource)` 并调用跟踪事件的方法 (`Activity1`)。</span><span class="sxs-lookup"><span data-stu-id="95dc2-116">The following code creates a new trace source (`mySource)` and calls a method (`Activity1`) that traces events.</span></span>  <span data-ttu-id="95dc2-117">跟踪消息是通过默认跟踪侦听器写入的。</span><span class="sxs-lookup"><span data-stu-id="95dc2-117">The trace messages are written by the default trace listener.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a><span data-ttu-id="95dc2-118">创建和初始化跟踪侦听器和筛选器</span><span class="sxs-lookup"><span data-stu-id="95dc2-118">To create and initialize trace listeners and filters</span></span>  
  
1.  <span data-ttu-id="95dc2-119">第一个过程中的代码不会以编程方式标识任何跟踪侦听器或筛选器。</span><span class="sxs-lookup"><span data-stu-id="95dc2-119">The code in the first procedure does not programmatically identify any trace listeners or filters.</span></span> <span data-ttu-id="95dc2-120">代码本身会产生写入到默认跟踪侦听器的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="95dc2-120">The code alone results in the trace messages being written to the default trace listener.</span></span> <span data-ttu-id="95dc2-121">若要配置特定的跟踪侦听器及其关联的筛选器，可编辑与应用程序名称对应的配置文件。</span><span class="sxs-lookup"><span data-stu-id="95dc2-121">To configure specific trace listeners and their associated filters, edit the configuration file that corresponds to the name of your application.</span></span> <span data-ttu-id="95dc2-122">在此文件中，可以添加或删除侦听器、为侦听器设置属性和筛选器或删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="95dc2-122">In this file, you can add or remove a listener, set the properties and filter for a listener, or remove listeners.</span></span> <span data-ttu-id="95dc2-123">以下配置文件示例演示如何为在前面过程中创建的跟踪源初始化控制台跟踪侦听器和文本编写器跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="95dc2-123">The following configuration file example shows how to initialize a console trace listener and a text writer trace listener for the trace source that is created in the preceding procedure.</span></span> <span data-ttu-id="95dc2-124">除配置跟踪侦听器外，配置文件还同时为这两个侦听器创建筛选器，并为跟踪源创建一个源开关。</span><span class="sxs-lookup"><span data-stu-id="95dc2-124">In addition to configuring the trace listeners, the configuration file creates filters for both of the listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="95dc2-125">其中演示了两种添加跟踪侦听器的技术：将侦听器直接添加到跟踪源，以及将侦听器添加到共享的侦听器集合，然后按名称将它添加到跟踪源。</span><span class="sxs-lookup"><span data-stu-id="95dc2-125">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="95dc2-126">为这两个侦听器标识的筛选器用不同的源级别进行初始化。</span><span class="sxs-lookup"><span data-stu-id="95dc2-126">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="95dc2-127">这样导致某些消息仅由其中一个侦听器编写。</span><span class="sxs-lookup"><span data-stu-id="95dc2-127">This results in some messages being written by only one of the two listeners.</span></span>  
  
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
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
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
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a><span data-ttu-id="95dc2-128">更改侦听器写入跟踪消息的级别</span><span class="sxs-lookup"><span data-stu-id="95dc2-128">To change the level at which a listener writes a trace message</span></span>  
  
1.  <span data-ttu-id="95dc2-129">配置文件在初始化应用程序时初始化跟踪源的设置。</span><span class="sxs-lookup"><span data-stu-id="95dc2-129">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="95dc2-130">若要更改这些设置，必须更改配置文件并重启应用，或使用 <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> 方法以编程方式刷新应用程序。</span><span class="sxs-lookup"><span data-stu-id="95dc2-130">To change those settings you must change the configuration file and restart the application or programmatically refresh the application using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="95dc2-131">应用程序可以动态更改配置文件设置的属性，以重写用户指定的任何设置。</span><span class="sxs-lookup"><span data-stu-id="95dc2-131">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span>  <span data-ttu-id="95dc2-132">例如，可能想要确保始终将关键消息发送到文本文件，而不管当前配置设置如何。</span><span class="sxs-lookup"><span data-stu-id="95dc2-132">For example, you might want to assure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified   
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =   
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures   
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners   
                // for all event types. This statement will override   
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,   
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,   
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="95dc2-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="95dc2-133">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventTypeFilter>  
 [<span data-ttu-id="95dc2-134">如何：创建和初始化跟踪源</span><span class="sxs-lookup"><span data-stu-id="95dc2-134">How to: Create and Initialize Trace Sources</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)  
 [<span data-ttu-id="95dc2-135">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="95dc2-135">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)
