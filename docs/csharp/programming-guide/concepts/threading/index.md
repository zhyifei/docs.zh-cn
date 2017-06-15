---
title: "线程处理 (C#) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e3f213b43c2f05a5afef1db7aec8b9c2695df989
ms.contentlocale: zh-cn
ms.lasthandoff: 06/15/2017

---
# <a name="threading-c"></a>线程处理 (C#)
线程处理使 C# 程序能够执行并发处理，以便您可以执行一次的多个操作。 例如，你可以使用线程处理监视来自用户的输入、 执行后台任务以及处理并发输入流。  
  
 线程具有以下属性：  
  
-   线程使程序能够执行并发处理。  
  
-   .NET Framework<xref:System.Threading>命名空间使得使用线程更容易。  
  
-   线程共享应用程序的资源。 有关详细信息，请参阅[使用线程和线程处理](https://msdn.microsoft.com/library/e1dx6b2h)。  
  
 默认情况下，C# 程序具有一个线程。 但是，还可以创建和使用与主线程的并行执行代码辅助线程。 这些线程通常称为*工作线程*。  
  
 工作线程可以用于而不会占用主线程中执行耗时或时间关键任务。 例如，工作线程通常用于在服务器应用程序而无需等待完成前面的请求响应传入的请求。 工作线程还用于在桌面应用程序中执行"后台"任务，以便主线程-驱动器用户界面元素-保持响应用户操作。  
  
 线程处理解决了问题吞吐量和响应能力，但它也可能引入资源共享问题，如死锁和争用条件。 多个线程特别适用于需要不同的资源，如文件句柄和网络连接的任务。 将多个线程分配给单个资源很可能会导致同步问题，并具有线程在等待其他线程时，经常阻止与使用多个线程的初衷背道而驰。  
  
 一个常见策略是使用工作线程执行耗时或不需要很多其他线程所使用的资源的时间关键任务。 当然，必须通过多个线程访问程序中的某些资源。 对于这些情况，<xref:System.Threading>命名空间提供用于同步线程的类。 这些类包括<xref:System.Threading.Mutex>， <xref:System.Threading.Monitor>， <xref:System.Threading.Interlocked>， <xref:System.Threading.AutoResetEvent>，和<xref:System.Threading.ManualResetEvent>。  
  
 你可以使用某些或所有这些类来同步活动的多个线程，但 C# 语言支持一些对线程处理支持。 例如， [Lock 语句](../../../../csharp/language-reference/keywords/lock-statement.md)提供同步功能通过隐式使用<xref:System.Threading.Monitor>。  
  
> [!NOTE]
>  开头[!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)]，使用极大地简化多线程的编程<xref:System.Threading.Tasks.Parallel?displayProperty=fullName>和<xref:System.Threading.Tasks.Task?displayProperty=fullName>类，[并行 LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688)，新的并发集合中的类<xref:System.Collections.Concurrent?displayProperty=fullName>命名空间，和新的编程模型所基于的任务，而不是线程的概念。 有关详细信息，请参阅[并行编程](https://msdn.microsoft.com/library/dd460693)。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[多线程应用程序 (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)|描述如何创建和使用线程。|  
|[参数和返回值的多线程过程 (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|描述如何将传递和返回参数与多线程应用程序。|  
|[演练： 利用 BackgroundWorker 组件 (C#) 的多线程处理](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|演示如何创建简单的多线程应用程序。|  
|[线程同步 (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)|介绍如何控制线程交互。|  
|[线程计时器 (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md)|描述如何在按固定时间间隔的单独线程上运行过程。|  
|[线程池 (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)|描述如何使用由系统管理的工作线程池。|  
|[如何： 使用线程池 (C#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|说明如何在线程池中的多个线程的同步的使用。|  
|[线程处理](https://msdn.microsoft.com/library/3e8s7xdd)|描述如何实现在.NET Framework 线程处理。|
