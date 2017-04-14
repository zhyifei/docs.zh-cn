---
title: "CLR ETW 提供程序 | Microsoft Docs"
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
  - "CLR ETW 提供程序"
  - "ETW, CLR 提供程序"
ms.assetid: 0beafad4-b2c8-47f4-b342-83411d57a51f
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# CLR ETW 提供程序
公共语言运行时 \(CLR\) 具有两个提供程序：运行时提供程序和断开提供程序。  
  
 运行时提供程序根据启用的关键字（事件的类别）引发相应事件。  例如，可以通过启用 `LoaderKeyword` 关键字来收集加载程序事件。  
  
 Windows 事件跟踪 \(ETW\) 事件记录在一个扩展名为 .etl 的文件中，稍后可以根据需要在逗号分隔值 \(.csv\) 文件中对该文件进行后期处理。  有关如何将 .etl 文件转换为 .csv 文件的信息，请参见[控制 .NET Framework 日志记录](../../../docs/framework/performance/controlling-logging.md)。  
  
## 运行时提供程序  
 运行时提供程序是主 CLR ETW 提供程序。  
  
 CLR 运行时提供程序 GUID 为 e13c0d23\-ccbc\-4e12\-931b\-d9cc2eee27e4。  
  
 有关如何使用常用工具记录并查看 CLR ETW 事件的示例，请参见[控制 .NET Framework 日志记录](../../../docs/framework/performance/controlling-logging.md)。  
  
 除了使用 `LoaderKeyword` 之类的关键字以外，您可能还必须启用用于记录可能会被过于频繁地引发的事件的关键字。  `StartEnumerationKeyword` 和 `EndEnumerationKeyword` 关键字可启用这些事件，[CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)中对这些关键字进行了总结。  
  
## 断开提供程序  
 对于某些特殊用途必须启用断开提供程序。  但对于大多数用户来说，运行时提供程序应该就足够了。  
  
 CLR 断开提供程序 GUID 为 A669021C\-C450\-4609\-A035\-5AF59AF4DF18。  
  
 通常情况下，在一个进程启动之前会启用 ETW 日志记录功能，并且日志记录功能会在该进程退出后关闭。  但是，如果在执行进程的过程中打开 ETW 日志记录功能，则需要有关进程的其他信息。  例如，对于符号解析，必须记录在启用日志记录功能前已经加载的方法的方法事件。  
  
 `DCStart` 和 `DCEnd` 事件可捕获数据收集开始和停止时的进程的状态。（状态是指高级别的信息，包括已实时 \(JIT\) 编译的方法和已加载的程序集。）这两个事件可以提供有关进程中已执行的操作的信息；例如，哪些方法已经过 JIT 编译等等。  
  
 在使用断开提供程序时只引发其名称中包含 `DC`、`DCStart`、`DCEnd` 或 `DCInit` 的事件。  而且，只有在使用断开提供程序时才会引发这些事件。  
  
 除事件关键字筛选器以外，断开提供程序还支持 `StartRundownKeyword` 和 `EndRundownKeyword` 关键字以便提供目标筛选。  
  
### 开始断开  
 如果使用 `StartRundownKeyword` 关键字启用断开提供程序的日志记录功能，则会触发开始断开。  这将导致引发 `DCStart` 事件并捕获系统的状态。  在开始枚举之前，将引发 `DCStartInit` 事件。  在结束枚举时，将引发 `DCStartComplete` 事件来通知控制器数据收集已正常终止。  
  
### 结束断开  
 如果使用 `EndRundownKeyword` 关键字启用断开提供程序的日志记录功能，则会触发结束断开。  结束断开将停止分析继续执行的进程。  `DCEnd` 事件可捕获系统在停止分析时的状态。  
  
 在开始枚举之前，将引发 `DCEndInit` 事件。  在结束枚举时，将引发 `DCEndComplete` 事件来通知使用者数据收集已正常终止。  开始断开和结束断开主要用于托管符号解析。  开始断开可以提供有关在开始分析会话前已经过 JIT 编译的方法的地址范围信息。  结束断开可以提供有关在分析将要关闭时已经过 JIT 编译的所有方法的地址范围信息。  
  
 当分析会话停止时不会自动发生结束断开。  相反，尝试执行托管符号解析的工具必须在即将停止分析之前，显式地调用 CLR 断开提供程序会话，同时启用 `EndRundownKeyword` 关键字。  
  
 尽管开始断开或结束断开都能够提供有关托管符号解析的方法地址范围信息，但建议您使用 `EndRundownKeyword` 关键字（提供 `DCEnd` 事件），而不要使用 `StartRundownKeyword` 关键字（提供 `DCStart` 事件）。  使用 `StartRundownKeyword` 会导致在分析会话运行期间发生断开，这可能会干扰所分析的方案。  
  
## 使用运行时提供程序和断开提供程序执行 ETW 数据收集  
 下面的示例演示如何以一种允许托管进程的符号解析并将影响减至最小的方式来使用 CLR 断开提供程序，而不考虑进程是在所分析的窗口内部还是在外部开始或结束的。  
  
1.  使用 CLR 运行时提供程序启用 ETW 日志记录功能：  
  
    ```  
    xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:0x5 -f clr1.etl      
    ```  
  
     日志将保存到 clr1.etl 文件中。  
  
2.  若要在进程继续执行的过程中停止分析，请启动断开提供程序以捕获 `DCEnd` 事件：  
  
    ```  
    xperf -start clrRundown -on A669021C-C450-4609-A035-5AF59AF4DF18:0xB8:0x5 -f clr2.etl      
    ```  
  
     这将使 `DCEnd` 事件的收集开始断开会话。  您可能需要等待 30 至 60 秒钟，以便收集完所有事件。  日志将保存到 clr1.et2 文件中。  
  
3.  关闭所有 ETW 分析：  
  
    ```  
    xperf -stop clrRundown   
    xperf -stop clr  
    ```  
  
4.  合并分析以便创建一个日志文件：  
  
    ```  
    xperf -merge -d clr1.etl clr2.etl merged.etl  
    ```  
  
     merged.etl 文件将包含来自运行时提供程序会话和断开提供程序会话的事件。  
  
 利用工具可以执行步骤 2 和步骤 3（开始断开会话然后终止分析），而不是在用户请求停止分析后立即关闭分析。  利用工具还可以执行步骤 4。  
  
## 请参阅  
 [公共语言运行时中的 ETW 事件](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)