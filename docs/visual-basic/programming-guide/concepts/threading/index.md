---
title: 线程处理 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
ms.openlocfilehash: 366c88db5d229120b1e626f275b4eeb8ecd42dba
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48844990"
---
# <a name="threading-visual-basic"></a>线程处理 (Visual Basic)
通过线程处理，Visual Basic 程序可以执行并发处理，从而能够一次执行多项操作。 例如，可使用线程处理来监视来自用户的输入、执行后台任务和处理并行输入流。  
  
 线程具有以下属性：  
  
-   程序可利用线程执行并行处理。  
  
-   The .NET Framework <xref:System.Threading> 命名空间简化了线程的使用。  
  
-   线程可共享应用程序的资源。 有关更多信息，请参见[使用线程和线程处理](../../../../standard/threading/using-threads-and-threading.md)。  
  
 Visual Basic 程序默认只有一个线程。 但是，可创建辅助线程，将其用于与主线程并行执行代码。 这些线程通常称为工作线程。  
  
 工作线程可用于执行耗时或时间关键型的任务，无需占用主线程。 例如，服务器应用程序中通常使用工作线程处理传入的请求，而不用等待上一个请求完成。 工作线程还用于在桌面应用程序中执行“后台”任务，让驱动用户界面元素的主线程仍然响应用户操作。  
  
 线程处理解决了吞吐量和响应性的问题，但也引入了死锁和争用条件等资源共享问题。 多线程特别适用于需要不同资源（如文件句柄和网络连接）的任务。 向单个资源分配多线程可能会导致同步问题，而若在等待其他线程时造成线程频繁受阻，这与使用多线程的目的背道而驰。  
  
 常见的策略是使用工作线程执行耗时或时间关键型的任务，这些任务不需要其他线程所用的很多资源。 当然，程序中的某些资源必须由多个线程访问。 对于这些情况，<xref:System.Threading> 命名空间提供了用于同步线程的类。 这些类包括 <xref:System.Threading.Mutex>、<xref:System.Threading.Monitor>、<xref:System.Threading.Interlocked>、<xref:System.Threading.AutoResetEvent> 和 <xref:System.Threading.ManualResetEvent>。  
  
 可以使用部分或全部类同步多线程的活动，但 Visual Basic 语言对线程处理提供一定程度的支持。 例如，[SynLock 语句](../../../../visual-basic/language-reference/statements/synclock-statement.md)通过隐式使用 <xref:System.Threading.Monitor> 提供同步功能。  
  
> [!NOTE]
>  自 [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)] 起，由于出现了 <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 类、[并行 LINQ (PLINQ)](../../../../standard/parallel-programming/parallel-linq-plinq.md)、<xref:System.Collections.Concurrent?displayProperty=nameWithType> 命名空间中的新并发集合类，以及基于任务（而非线程）概念的新编程模型，多线程编程得到了大幅简化。 有关详细信息，请参阅[并行编程](../../../../standard/parallel-programming/index.md)。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[线程处理](../../../../standard/threading/index.md)|描述如何在 .NET Framework 中实现线程处理。|
