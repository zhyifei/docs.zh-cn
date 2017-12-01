---
title: "托管线程处理基本知识"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a>托管线程处理基本知识
本部分的前五个主题旨在帮助你确定何时使用托管线程处理，并介绍一些基本功能。 提供其他功能的类的信息，请参阅[线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)和[同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)。  
  
 在此部分涵盖的主题的其余部分高级主题，包括托管线程处理与 Windows 操作系统的系统的交互。  
  
> [!NOTE]
>  在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，任务并行库和 PLINQ 提供的 Api 来多线程程序中的任务和数据并行。 有关详细信息，请参阅[并行编程](../../../docs/standard/parallel-programming/index.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [线程与线程处理](../../../docs/standard/threading/threads-and-threading.md)  
 讨论的优点和缺点的多个线程，并概述了你可能创建线程或使用线程池线程的方案。  
  
 [托管线程中的异常](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 描述针对不同版本的.NET Framework 中，线程中的未处理异常的行为尤其情况中它们可以导致应用终止。  
  
 [为多线程处理同步数据](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 介绍了同步用于多个线程的类中的数据的策略。  
  
 [托管线程状态](../../../docs/standard/threading/managed-thread-states.md)  
 介绍基本的线程状态，并说明如何检测是否正在运行一个线程。  
  
 [前台和后台线程](../../../docs/standard/threading/foreground-and-background-threads.md)  
 介绍前景色和背景线程之间的差异。  
  
 [Windows 中的托管和非托管线程](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 讨论托管和非托管线程处理之间的关系、 windows 线程处理 Api，列出托管等效项和讨论 COM 单元和托管的线程的交互。  
  
 [Thread.Suspend、垃圾回收和安全点](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 描述线程挂起和垃圾回收。  
  
 [线程本地存储：线程相关的静态字段和数据槽](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 介绍线程相关的存储机制。  
  
 [托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 描述如何异步操作或长时间运行的同步操作可通过使用取消标记被取消。  
  
## <a name="reference"></a>参考  
 <xref:System.Threading.Thread>  
 提供**线程**类的参考文档，无论该类是来自托管代码还是在托管应用程序中创建的，它都表示一个托管线程。  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 提供一种安全的方法，以实现多线程处理与用户界面对象结合使用。  
  
## <a name="related-sections"></a>相关章节  
 [同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 介绍用于同步多个线程的活动的托管的类。  
  
 [托管线程处理的最佳做法](../../../docs/standard/threading/managed-threading-best-practices.md)  
 描述常见的问题的多线程处理的避免出现的问题和策略。  
  
 [并行编程](../../../docs/standard/parallel-programming/index.md)  
 描述任务并行库和 PLINQ 中，极大地简化了创建异步和多线程的.NET Framework 应用程序的工作。
