---
title: 套接字
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
ms.openlocfilehash: 4a1b18f2c31bf8dad8cf32e2e5205cf3008e7b18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136040"
---
# <a name="sockets"></a><span data-ttu-id="ccc5c-102">套接字</span><span class="sxs-lookup"><span data-stu-id="ccc5c-102">Sockets</span></span>
<span data-ttu-id="ccc5c-103"><xref:System.Net.Sockets> 命名空间包含 Windows 套接字接口的托管实现。</span><span class="sxs-lookup"><span data-stu-id="ccc5c-103">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="ccc5c-104"><xref:System.Net> 命名空间中的所有其他网络访问类均建立在套接字的此实现之上。</span><span class="sxs-lookup"><span data-stu-id="ccc5c-104">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="ccc5c-105">.NET Framework <xref:System.Net.Sockets.Socket> 类是由 Winsock32 API 提供的套接字服务的托管代码版本。</span><span class="sxs-lookup"><span data-stu-id="ccc5c-105">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="ccc5c-106">大多数情况下，Socket 类方法只是将数据封送到其本机 Win32 对等体中，并负责任何必要的安全检查。</span><span class="sxs-lookup"><span data-stu-id="ccc5c-106">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="ccc5c-107">Socket 类支持同步和异步两种基本模式。</span><span class="sxs-lookup"><span data-stu-id="ccc5c-107">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="ccc5c-108">在同步模式下，对执行网络操作（例如 <xref:System.Net.Sockets.Socket.Send%2A> 和 <xref:System.Net.Sockets.Socket.Receive%2A>）的函数的调用等待操作完成，再将控制权返回给调用程序。</span><span class="sxs-lookup"><span data-stu-id="ccc5c-108">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="ccc5c-109">在异步模式下，这些调用立即返回。</span><span class="sxs-lookup"><span data-stu-id="ccc5c-109">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc5c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccc5c-110">See also</span></span>

- [<span data-ttu-id="ccc5c-111">如何：创建套接字</span><span class="sxs-lookup"><span data-stu-id="ccc5c-111">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)

- [<span data-ttu-id="ccc5c-112">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="ccc5c-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
