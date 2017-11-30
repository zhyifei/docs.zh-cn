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
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="5e555-102">如何：使用匿名管道进行本地进程间通信</span><span class="sxs-lookup"><span data-stu-id="5e555-102">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="5e555-103">匿名管道在本地计算机上提供进程间通信。</span><span class="sxs-lookup"><span data-stu-id="5e555-103">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="5e555-104">它们提供的功能比命名管道少，但所需要的系统开销也少。</span><span class="sxs-lookup"><span data-stu-id="5e555-104">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="5e555-105">匿名管道可用于简化本地计算机上的进程间通信。</span><span class="sxs-lookup"><span data-stu-id="5e555-105">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="5e555-106">你无法通过网络将用于通信的匿名管道。</span><span class="sxs-lookup"><span data-stu-id="5e555-106">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="5e555-107">若要实现匿名管道，请使用 <xref:System.IO.Pipes.AnonymousPipeServerStream> 和 <xref:System.IO.Pipes.AnonymousPipeClientStream> 类。</span><span class="sxs-lookup"><span data-stu-id="5e555-107">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e555-108">示例</span><span class="sxs-lookup"><span data-stu-id="5e555-108">Example</span></span>  
 <span data-ttu-id="5e555-109">下面的示例演示了如何将字符串从父进程发送到使用匿名管道的子进程。</span><span class="sxs-lookup"><span data-stu-id="5e555-109">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="5e555-110">此示例将创建<xref:System.IO.Pipes.AnonymousPipeServerStream>父进程中的对象<xref:System.IO.Pipes.PipeDirection>值<xref:System.IO.Pipes.PipeDirection.Out>。</span><span class="sxs-lookup"><span data-stu-id="5e555-110">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="5e555-111">父进程然后，通过使用客户端句柄创建创建子进程<xref:System.IO.Pipes.AnonymousPipeClientStream>对象。</span><span class="sxs-lookup"><span data-stu-id="5e555-111">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="5e555-112">子进程具有<xref:System.IO.Pipes.PipeDirection>值<xref:System.IO.Pipes.PipeDirection.In>。</span><span class="sxs-lookup"><span data-stu-id="5e555-112">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="5e555-113">父进程随后发送至子进程的用户提供的字符串。</span><span class="sxs-lookup"><span data-stu-id="5e555-113">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="5e555-114">该字符串显示到子进程中的控制台中。</span><span class="sxs-lookup"><span data-stu-id="5e555-114">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="5e555-115">下面的示例演示服务器进程。</span><span class="sxs-lookup"><span data-stu-id="5e555-115">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="5e555-116">示例</span><span class="sxs-lookup"><span data-stu-id="5e555-116">Example</span></span>  
 <span data-ttu-id="5e555-117">下面的示例演示客户端进程。</span><span class="sxs-lookup"><span data-stu-id="5e555-117">The following example shows the client process.</span></span> <span data-ttu-id="5e555-118">服务器进程启动的客户端过程，并为该进程提供的客户端句柄。</span><span class="sxs-lookup"><span data-stu-id="5e555-118">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="5e555-119">从客户端代码生成的可执行文件应命名`pipeClient.exe`并复制到服务器之前运行的服务器进程可执行文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="5e555-119">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="5e555-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e555-120">See Also</span></span>  
 [<span data-ttu-id="5e555-121">管道</span><span class="sxs-lookup"><span data-stu-id="5e555-121">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="5e555-122">如何：使用命名管道进行网络进程间通信</span><span class="sxs-lookup"><span data-stu-id="5e555-122">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
