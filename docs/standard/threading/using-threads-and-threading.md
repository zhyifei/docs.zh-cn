---
title: "使用线程和线程处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80eb4c3bb98acdd1f83dbf5bcf57b2f7b295742b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-threads-and-threading"></a>使用线程和线程处理
本部分中的主题讨论的创建和管理托管的线程、 如何将数据传递给托管线程和返回结果，以及如何销毁线程和处理<xref:System.Threading.ThreadAbortException>。  
  
## <a name="in-this-section"></a>本节内容  
 [启动时创建线程并传递数据](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 讨论并演示了如何创建托管线程，包括如何将数据传递到新线程和如何取回数据。  
  
 [暂停和恢复线程](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 讨论暂停和继续执行托管的线程的后果。  
  
 [销毁线程](../../../docs/standard/threading/destroying-threads.md)  
 讨论销毁托管的线程，以及如何处理的后果<xref:System.Threading.ThreadAbortException>。  
  
 [计划线程](../../../docs/standard/threading/scheduling-threads.md)  
 讨论线程优先级以及它们如何影响线程计划。  
  
## <a name="reference"></a>参考  
 <xref:System.Threading.Thread>  
 提供的参考文档<xref:System.Threading.Thread>类，该类表示托管的线程，无论它来自非托管代码还是在托管应用程序中创建。  
  
 <xref:System.Threading.ThreadStart>  
 提供的参考文档<xref:System.Threading.ThreadStart>委托，表示无参数的线程过程。  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 可以轻松地将数据传递给一个线程的过程，不使用强类型。  
  
## <a name="related-sections"></a>相关章节  
 [线程与线程处理](../../../docs/standard/threading/threads-and-threading.md)  
 提供对托管线程处理的介绍。
