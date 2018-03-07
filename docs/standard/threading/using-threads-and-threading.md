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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5bed13950a29cfa787ef8c9eb2608c6d74dfd49f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="using-threads-and-threading"></a>使用线程和线程处理
本节中的主题介绍了如何创建和管理托管线程、如何向托管线程传递数据并返回结果，以及如何销毁线程和处理 <xref:System.Threading.ThreadAbortException>。  
  
## <a name="in-this-section"></a>本节内容  
 [启动时创建线程并传递数据](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 介绍并展示了如何创建托管线程，包括如何向新线程传递数据和返回数据。  
  
 [暂停和恢复线程](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 介绍了暂停和恢复托管线程的后果。  
  
 [销毁线程](../../../docs/standard/threading/destroying-threads.md)  
 介绍了销毁托管线程的后果，以及如何处理 <xref:System.Threading.ThreadAbortException>。  
  
 [计划线程](../../../docs/standard/threading/scheduling-threads.md)  
 介绍了线程优先级及其如何影响线程计划。  
  
## <a name="reference"></a>参考  
 <xref:System.Threading.Thread>  
 收录了 <xref:System.Threading.Thread> 类的参考文档，无论此类是来自非托管代码，还是在托管应用中创建，它都表示托管线程。  
  
 <xref:System.Threading.ThreadStart>  
 收录了表示无参数线程过程的 <xref:System.Threading.ThreadStart> 委托的参考文档。  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 提供了将数据轻松传递给线程过程的方法，尽管没有强类型化。  
  
## <a name="related-sections"></a>相关章节  
 [线程与线程处理](../../../docs/standard/threading/threads-and-threading.md)  
 介绍了托管线程。
