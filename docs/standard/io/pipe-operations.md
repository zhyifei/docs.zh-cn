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
# <a name="pipe-operations-in-the-net-framework"></a><span data-ttu-id="9ec04-102">.NET Framework 中的管道操作</span><span class="sxs-lookup"><span data-stu-id="9ec04-102">Pipe Operations in the .NET Framework</span></span>
<span data-ttu-id="9ec04-103">管道提供一种进程间通信。</span><span class="sxs-lookup"><span data-stu-id="9ec04-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="9ec04-104">有两种类型的管道：</span><span class="sxs-lookup"><span data-stu-id="9ec04-104">There are two types of pipes:</span></span>  
  
-   <span data-ttu-id="9ec04-105">匿名管道。</span><span class="sxs-lookup"><span data-stu-id="9ec04-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="9ec04-106">匿名管道在本地计算机上提供进程间通信。</span><span class="sxs-lookup"><span data-stu-id="9ec04-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="9ec04-107">匿名管道需要较少的开销比命名管道，但提供有限的服务。</span><span class="sxs-lookup"><span data-stu-id="9ec04-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="9ec04-108">匿名管道是单向的并且不通过网络使用。</span><span class="sxs-lookup"><span data-stu-id="9ec04-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="9ec04-109">它们仅支持单个服务器实例。</span><span class="sxs-lookup"><span data-stu-id="9ec04-109">They support only a single server instance.</span></span> <span data-ttu-id="9ec04-110">匿名管道可用于之间其中管道句柄可以轻松地传递给子进程时创建的父和子进程或线程间通信。</span><span class="sxs-lookup"><span data-stu-id="9ec04-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="9ec04-111">在 .NET Framework 中，可通过使用 <xref:System.IO.Pipes.AnonymousPipeServerStream> 和 <xref:System.IO.Pipes.AnonymousPipeClientStream> 类来实现匿名管道。</span><span class="sxs-lookup"><span data-stu-id="9ec04-111">In the .NET Framework, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="9ec04-112">请参阅[如何： 使用匿名管道进行本地进程间通信](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec04-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
-   <span data-ttu-id="9ec04-113">命名的管道。</span><span class="sxs-lookup"><span data-stu-id="9ec04-113">Named pipes.</span></span>  
  
     <span data-ttu-id="9ec04-114">命名的管道提供的管道服务器和一个或多个管道客户端之间的进程间通信。</span><span class="sxs-lookup"><span data-stu-id="9ec04-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="9ec04-115">命名的管道可以是单向或双工。</span><span class="sxs-lookup"><span data-stu-id="9ec04-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="9ec04-116">它们支持基于消息的通信，并允许多个客户端同时连接到使用同一管道名称的服务器进程。</span><span class="sxs-lookup"><span data-stu-id="9ec04-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="9ec04-117">命名的管道还支持模拟，这样连接进程便在远程服务器上使用它们自己的权限。</span><span class="sxs-lookup"><span data-stu-id="9ec04-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="9ec04-118">在 .NET Framework 中，可通过使用 <xref:System.IO.Pipes.NamedPipeServerStream> 和 <xref:System.IO.Pipes.NamedPipeClientStream> 类来实现命名管道。</span><span class="sxs-lookup"><span data-stu-id="9ec04-118">In the .NET Framework, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="9ec04-119">请参阅[如何： 使用命名管道进行网络进程间通信](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec04-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec04-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ec04-120">See Also</span></span>  
 [<span data-ttu-id="9ec04-121">文件和流 I-O</span><span class="sxs-lookup"><span data-stu-id="9ec04-121">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="9ec04-122">如何：使用匿名管道进行本地进程间通信</span><span class="sxs-lookup"><span data-stu-id="9ec04-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [<span data-ttu-id="9ec04-123">如何：使用命名管道进行网络进程间通信</span><span class="sxs-lookup"><span data-stu-id="9ec04-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
