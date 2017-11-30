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
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="1102c-102">如何：使用命名管道进行网络进程间通信</span><span class="sxs-lookup"><span data-stu-id="1102c-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="1102c-103">命名的管道提供的管道服务器和一个或多个管道客户端之间的进程间通信。</span><span class="sxs-lookup"><span data-stu-id="1102c-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="1102c-104">它们比匿名管道（用于在本地计算机上提供进程间的通信）提供更多的功能。</span><span class="sxs-lookup"><span data-stu-id="1102c-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="1102c-105">命名管道支持跨网络和多个服务器实例的全双工通信、基于消息的通信以及客户端模拟，这样连接进程便可在远程服务器上使用自己的权限集。</span><span class="sxs-lookup"><span data-stu-id="1102c-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="1102c-106">若要实现名称管道，请使用 <xref:System.IO.Pipes.NamedPipeServerStream> 和 <xref:System.IO.Pipes.NamedPipeClientStream> 类。</span><span class="sxs-lookup"><span data-stu-id="1102c-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1102c-107">示例</span><span class="sxs-lookup"><span data-stu-id="1102c-107">Example</span></span>  
 <span data-ttu-id="1102c-108">下面的示例演示如何通过使用创建命名的管道<xref:System.IO.Pipes.NamedPipeServerStream>类。</span><span class="sxs-lookup"><span data-stu-id="1102c-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="1102c-109">在此示例中，服务器进程创建四个线程。</span><span class="sxs-lookup"><span data-stu-id="1102c-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="1102c-110">每个线程可以接受的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="1102c-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="1102c-111">连接的客户端进程然后向服务器提供的文件名称。</span><span class="sxs-lookup"><span data-stu-id="1102c-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="1102c-112">如果客户端具有足够的权限，服务器进程中打开的文件，并将其内容发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="1102c-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="1102c-113">示例</span><span class="sxs-lookup"><span data-stu-id="1102c-113">Example</span></span>  
 <span data-ttu-id="1102c-114">下面的示例演示客户端过程中，使用<xref:System.IO.Pipes.NamedPipeClientStream>类。</span><span class="sxs-lookup"><span data-stu-id="1102c-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="1102c-115">客户端连接到的服务器进程，并向服务器发送的文件名称。</span><span class="sxs-lookup"><span data-stu-id="1102c-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="1102c-116">该示例使用模拟，因此正在运行客户端应用程序的标识必须有权访问该文件。</span><span class="sxs-lookup"><span data-stu-id="1102c-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="1102c-117">然后，服务器将文件的内容发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="1102c-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="1102c-118">文件内容将显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="1102c-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="1102c-119">可靠编程</span><span class="sxs-lookup"><span data-stu-id="1102c-119">Robust Programming</span></span>  
 <span data-ttu-id="1102c-120">在此示例中的客户端和服务器进程用于运行在同一计算机上，因此服务器名称提供给<xref:System.IO.Pipes.NamedPipeClientStream>对象是`"."`。</span><span class="sxs-lookup"><span data-stu-id="1102c-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="1102c-121">如果客户端和服务器进程不同计算机上，`"."`将替换为运行的服务器进程的计算机的网络名称。</span><span class="sxs-lookup"><span data-stu-id="1102c-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1102c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1102c-122">See Also</span></span>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [<span data-ttu-id="1102c-123">管道</span><span class="sxs-lookup"><span data-stu-id="1102c-123">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="1102c-124">如何：使用匿名管道进行本地进程间通信</span><span class="sxs-lookup"><span data-stu-id="1102c-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
