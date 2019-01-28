---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
ms.openlocfilehash: 70a40ea79a7f8993005607b0dd5a05f43597b003
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714014"
---
# <a name="httplistener"></a><span data-ttu-id="a0622-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="a0622-102">HttpListener</span></span>
<span data-ttu-id="a0622-103"><xref:System.Net.HttpListener> 类提供一个可通过编程方式控制的 HTTP 协议侦听器。</span><span class="sxs-lookup"><span data-stu-id="a0622-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="a0622-104">侦听器在 <xref:System.Net.HttpListener> 对象的生存期内处于活动状态，在你的应用程序中运行。</span><span class="sxs-lookup"><span data-stu-id="a0622-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="a0622-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="a0622-105">HTTP.SYS</span></span>  
 <span data-ttu-id="a0622-106"><xref:System.Net.HttpListener> 类在 HTTP.sys 的基础上构建，后者是为 Windows 处理所有 HTTP 流量的内核模式侦听器。</span><span class="sxs-lookup"><span data-stu-id="a0622-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="a0622-107">HTTP.sys 提供连接管理、带宽限制以及 Web 服务器日志记录。</span><span class="sxs-lookup"><span data-stu-id="a0622-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="a0622-108">使用 `HttpCfg.exe` 工具可添加 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="a0622-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="a0622-109">有关详细信息，请参阅[服务器](https://go.microsoft.com/fwlink/?LinkID=178285)文档中的 [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) 工具相关文档。</span><span class="sxs-lookup"><span data-stu-id="a0622-109">For more information, see the documentation on the [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](https://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0622-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0622-110">See also</span></span>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.HttpWebResponse>
- [<span data-ttu-id="a0622-111">HTTP 服务器</span><span class="sxs-lookup"><span data-stu-id="a0622-111">HTTP Server</span></span>](https://go.microsoft.com/fwlink/?LinkID=178285)
- [<span data-ttu-id="a0622-112">Internet 信息中的安全性增强功能</span><span class="sxs-lookup"><span data-stu-id="a0622-112">Security Enhancements in Internet Information</span></span>](https://go.microsoft.com/fwlink/?LinkID=178286)
- [<span data-ttu-id="a0622-113">HttpListener ASPX 主机应用程序示例</span><span class="sxs-lookup"><span data-stu-id="a0622-113">HttpListener ASPX Host Application Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179560)
- [<span data-ttu-id="a0622-114">HttpListener 技术示例</span><span class="sxs-lookup"><span data-stu-id="a0622-114">HttpListener Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179558)
- [<span data-ttu-id="a0622-115">网络编程示例</span><span class="sxs-lookup"><span data-stu-id="a0622-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
