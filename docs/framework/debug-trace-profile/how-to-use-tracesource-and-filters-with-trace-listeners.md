---
title: "How to: Use TraceSource and Filters with Trace Listeners | Microsoft Docs"
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
  - "initializing trace listeners"
  - "configuration files [.NET Framework], trace listeners"
  - "app.config files, trace listeners"
  - "levels of writing trace messages"
  - "trace listeners, TraceSource class"
  - "application configuration files, trace listeners"
  - "filters, trace listeners"
  - "TraceSource class, trace listeners"
  - "trace listeners, creating"
  - "trace listeners, filters"
  - "trace listeners, initializing"
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Use TraceSource and Filters with Trace Listeners
.NET Framework 2.0 版中的新功能之一就是增强的跟踪系统。  基本的前提并未改变：跟踪消息通过开关发送到侦听器，侦听器则向关联的输出介质报告数据。  2.0 版的一个主要区别在于，可通过 <xref:System.Diagnostics.TraceSource> 类的实例启动跟踪。  <xref:System.Diagnostics.TraceSource> 旨在用作一个增强的跟踪系统，并且可代替较早的 <xref:System.Diagnostics.Trace> 和 <xref:System.Diagnostics.Debug> 跟踪类的静态方法使用。  熟悉的 <xref:System.Diagnostics.Trace> 和 <xref:System.Diagnostics.Debug> 类仍然存在，不过建议的做法是使用 <xref:System.Diagnostics.TraceSource> 类进行跟踪。  
  
 本主题介绍如何结合应用程序配置文件使用 <xref:System.Diagnostics.TraceSource>。虽然不建议使用 <xref:System.Diagnostics.TraceSource> 而不使用配置文件进行跟踪，但也可以这样做。  有关不使用配置文件的跟踪的信息，请参见[如何：创建和初始化跟踪源](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)。  
  
### 创建和初始化跟踪源  
  
1.  使用跟踪检测应用程序的第一步是创建跟踪源。  在具有不同组件的大项目中，可以为每个组件创建单独的跟踪源。  建议的做法是使用应用程序名称作为跟踪源名称。  这样将使不同的跟踪更容易保持独立。  下面的代码创建一个新的跟踪源 \(`mySource)`，并调用一个跟踪事件的方法 \(`Activity1`\)。跟踪消息由默认跟踪侦听器编写。  
  
    ```  
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
  
### 创建和初始化跟踪侦听器和筛选器  
  
1.  第一个过程中的代码未以编程方式标识任何跟踪侦听器或筛选器。  该代码自己导致跟踪消息被写到默认跟踪侦听器。  若要配置特定跟踪侦听器和它们的关联筛选器，请编辑对应于应用程序名称的配置文件。  在此文件中，您可以添加或移除某个侦听器，设置某个侦听器的属性和筛选器，或移除多个侦听器。  下面的配置文件示例演示如何为在上述过程中创建的跟踪源初始化控制台跟踪侦听器和文本编写器跟踪侦听器。  除了配置跟踪侦听器外，配置文件还同时为这两个侦听器创建筛选器，并为跟踪源创建一个源开关。  其中演示了两种添加跟踪侦听器的技术：将侦听器直接添加到跟踪源，以及将侦听器添加到共享的侦听器集合，然后按名称将它添加到跟踪源。  为这两个侦听器标识的筛选器用不同的源级别进行初始化。  这样导致某些消息仅由其中一个侦听器编写。  
  
    ```  
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
  
### 更改侦听器编写跟踪消息的级别  
  
1.  配置文件在初始化应用程序时初始化跟踪源的设置。  若要更改那些设置，必须更改配置文件并重新启动应用程序，或使用 <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName> 方法以编程方式刷新应用程序。  应用程序可以动态更改配置文件设置的属性，以重写用户指定的任何设置。例如，您可能想要确保始终将关键消息发送到文本文件，而不管当前配置设置如何。  
  
    ```  
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
  
## 请参阅  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.EventTypeFilter>   
 [如何：创建和初始化跟踪源](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)