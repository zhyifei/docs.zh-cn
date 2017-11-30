---
title: "如何：使用命名管道进行网络进程间通信"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communcation [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 952600e71311184c4a4f906734addbf335d0358a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>如何：使用命名管道进行网络进程间通信
命名的管道提供的管道服务器和一个或多个管道客户端之间的进程间通信。 它们比匿名管道（用于在本地计算机上提供进程间的通信）提供更多的功能。 命名管道支持跨网络和多个服务器实例的全双工通信、基于消息的通信以及客户端模拟，这样连接进程便可在远程服务器上使用自己的权限集。  
  
 若要实现名称管道，请使用 <xref:System.IO.Pipes.NamedPipeServerStream> 和 <xref:System.IO.Pipes.NamedPipeClientStream> 类。  
  
## <a name="example"></a>示例  
 下面的示例演示如何通过使用创建命名的管道<xref:System.IO.Pipes.NamedPipeServerStream>类。 在此示例中，服务器进程创建四个线程。 每个线程可以接受的客户端连接。 连接的客户端进程然后向服务器提供的文件名称。 如果客户端具有足够的权限，服务器进程中打开的文件，并将其内容发送回客户端。  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>示例  
 下面的示例演示客户端过程中，使用<xref:System.IO.Pipes.NamedPipeClientStream>类。 客户端连接到的服务器进程，并向服务器发送的文件名称。 该示例使用模拟，因此正在运行客户端应用程序的标识必须有权访问该文件。 然后，服务器将文件的内容发送回客户端。 文件内容将显示到控制台。  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>可靠编程  
 在此示例中的客户端和服务器进程用于运行在同一计算机上，因此服务器名称提供给<xref:System.IO.Pipes.NamedPipeClientStream>对象是`"."`。 如果客户端和服务器进程不同计算机上，`"."`将替换为运行的服务器进程的计算机的网络名称。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [管道](../../../docs/standard/io/pipe-operations.md)  
 [如何：使用匿名管道进行本地进程间通信](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
