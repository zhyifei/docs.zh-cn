---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: b4b8c1e916aa9382d156a197fa15c2e72e900a1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="httplistener"></a><span data-ttu-id="76843-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="76843-102">HttpListener</span></span>
<span data-ttu-id="76843-103"><xref:System.Net.HttpListener> 类提供一个可通过编程方式控制的 HTTP 协议侦听器。</span><span class="sxs-lookup"><span data-stu-id="76843-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="76843-104">侦听器在 <xref:System.Net.HttpListener> 对象的生存期内处于活动状态，在你的应用程序中运行。</span><span class="sxs-lookup"><span data-stu-id="76843-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="76843-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="76843-105">HTTP.SYS</span></span>  
 <span data-ttu-id="76843-106"><xref:System.Net.HttpListener> 类在 HTTP.sys 的基础上构建，后者是为 Windows 处理所有 HTTP 流量的内核模式侦听器。</span><span class="sxs-lookup"><span data-stu-id="76843-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="76843-107">HTTP.sys 提供连接管理、带宽限制以及 Web 服务器日志记录。</span><span class="sxs-lookup"><span data-stu-id="76843-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="76843-108">使用 `HttpCfg.exe` 工具可添加 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="76843-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="76843-109">有关详细信息，请参阅[服务器](http://go.microsoft.com/fwlink/?LinkID=178285)文档中的 [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) 工具相关文档。</span><span class="sxs-lookup"><span data-stu-id="76843-109">For more information, see the documentation on the [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](http://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76843-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="76843-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="76843-111">HTTP 服务器</span><span class="sxs-lookup"><span data-stu-id="76843-111">HTTP Server</span></span>](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="76843-112">Internet 信息中的安全增强功能</span><span class="sxs-lookup"><span data-stu-id="76843-112">Security Enhancements in Internet Information</span></span>](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="76843-113">HttpListener ASPX 主机应用程序示例</span><span class="sxs-lookup"><span data-stu-id="76843-113">HttpListener ASPX Host Application Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="76843-114">HttpListener 技术示例</span><span class="sxs-lookup"><span data-stu-id="76843-114">HttpListener Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="76843-115">网络编程示例</span><span class="sxs-lookup"><span data-stu-id="76843-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
