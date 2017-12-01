---
title: "前台和后台线程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a>前台和后台线程
托管的线程是后台线程或前台线程。 后台线程相等前台线程有一个例外： 后台线程不会保留运行的托管的执行环境。 一旦所有前台线程已都停止 （其中的.exe 文件是托管程序集） 的托管进程中，系统将停止所有后台线程，并关闭。  
  
> [!NOTE]
>  当运行时停止后台线程，因为进程正在关闭时，线程中不引发任何异常。 但是，当线程将停止，因为<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>方法卸载应用程序域中，<xref:System.Threading.ThreadAbortException>在前台和后台线程中引发。  
  
 使用<xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>属性来确定线程是背景或前景线程，或更改其状态。 线程可以更改为后台线程在任何时候通过设置其<xref:System.Threading.Thread.IsBackground%2A>属性`true`。  
  
> [!IMPORTANT]
>  前台或后台线程的状态的不会影响在线程中未经处理的异常的结果。 在.NET Framework 2.0 版中，在前台或后台线程中未经处理的异常会导致应用终止。 请参阅[托管线程中的异常](../../../docs/standard/threading/exceptions-in-managed-threads.md)。  
  
 属于托管的线程池的线程 (即，线程其<xref:System.Threading.Thread.IsThreadPoolThread%2A>属性是`true`) 是后台线程。 从非托管代码进入托管的执行环境的所有线程都标记为后台线程。 通过创建并启动一个新生成的所有线程<xref:System.Threading.Thread>对象是由默认前台线程。  
  
 如果你使用一个线程来监视活动，例如套接字连接，设置其<xref:System.Threading.Thread.IsBackground%2A>属性`true`，以便线程不会阻止您的进程终止。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
