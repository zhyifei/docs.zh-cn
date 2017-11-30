---
title: ".NET Framework 中的管道操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>.NET Framework 中的管道操作
管道提供一种进程间通信。 有两种类型的管道：  
  
-   匿名管道。  
  
     匿名管道在本地计算机上提供进程间通信。 匿名管道需要较少的开销比命名管道，但提供有限的服务。 匿名管道是单向的并且不通过网络使用。 它们仅支持单个服务器实例。 匿名管道可用于之间其中管道句柄可以轻松地传递给子进程时创建的父和子进程或线程间通信。  
  
     在 .NET Framework 中，可通过使用 <xref:System.IO.Pipes.AnonymousPipeServerStream> 和 <xref:System.IO.Pipes.AnonymousPipeClientStream> 类来实现匿名管道。  
  
     请参阅[如何： 使用匿名管道进行本地进程间通信](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)。  
  
-   命名的管道。  
  
     命名的管道提供的管道服务器和一个或多个管道客户端之间的进程间通信。 命名的管道可以是单向或双工。 它们支持基于消息的通信，并允许多个客户端同时连接到使用同一管道名称的服务器进程。 命名的管道还支持模拟，这样连接进程便在远程服务器上使用它们自己的权限。  
  
     在 .NET Framework 中，可通过使用 <xref:System.IO.Pipes.NamedPipeServerStream> 和 <xref:System.IO.Pipes.NamedPipeClientStream> 类来实现命名管道。  
  
     请参阅[如何： 使用命名管道进行网络进程间通信](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)。  
  
## <a name="see-also"></a>另请参阅  
 [文件和流 I-O](../../../docs/standard/io/index.md)  
 [如何：使用匿名管道进行本地进程间通信](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [如何：使用命名管道进行网络进程间通信](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
