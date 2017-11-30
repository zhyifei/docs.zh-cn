---
title: "如何：使用匿名管道进行本地进程间通信"
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
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f457cc91e6fbfc118e5363d1b0a8e8c2ad800748
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a>如何：使用匿名管道进行本地进程间通信
匿名管道在本地计算机上提供进程间通信。 它们提供的功能比命名管道少，但所需要的系统开销也少。 匿名管道可用于简化本地计算机上的进程间通信。 你无法通过网络将用于通信的匿名管道。  
  
 若要实现匿名管道，请使用 <xref:System.IO.Pipes.AnonymousPipeServerStream> 和 <xref:System.IO.Pipes.AnonymousPipeClientStream> 类。  
  
## <a name="example"></a>示例  
 下面的示例演示了如何将字符串从父进程发送到使用匿名管道的子进程。 此示例将创建<xref:System.IO.Pipes.AnonymousPipeServerStream>父进程中的对象<xref:System.IO.Pipes.PipeDirection>值<xref:System.IO.Pipes.PipeDirection.Out>。 父进程然后，通过使用客户端句柄创建创建子进程<xref:System.IO.Pipes.AnonymousPipeClientStream>对象。 子进程具有<xref:System.IO.Pipes.PipeDirection>值<xref:System.IO.Pipes.PipeDirection.In>。  
  
 父进程随后发送至子进程的用户提供的字符串。 该字符串显示到子进程中的控制台中。  
  
 下面的示例演示服务器进程。  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## <a name="example"></a>示例  
 下面的示例演示客户端进程。 服务器进程启动的客户端过程，并为该进程提供的客户端句柄。 从客户端代码生成的可执行文件应命名`pipeClient.exe`并复制到服务器之前运行的服务器进程可执行文件所在的目录。  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a>另请参阅  
 [管道](../../../docs/standard/io/pipe-operations.md)  
 [如何：使用命名管道进行网络进程间通信](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
