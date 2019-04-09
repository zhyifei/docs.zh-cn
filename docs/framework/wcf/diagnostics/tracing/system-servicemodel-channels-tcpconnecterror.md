---
title: System.ServiceModel.Channels.TcpConnectError
ms.date: 03/30/2017
ms.assetid: 22d93797-072e-405d-a3e0-5c519ddf290b
ms.openlocfilehash: 0bfd35e2b3ca421745701a91f2a5bfc91f3063aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091442"
---
# <a name="systemservicemodelchannelstcpconnecterror"></a><span data-ttu-id="3cdf9-102">System.ServiceModel.Channels.TcpConnectError</span><span class="sxs-lookup"><span data-stu-id="3cdf9-102">System.ServiceModel.Channels.TcpConnectError</span></span>
<span data-ttu-id="3cdf9-103">TCP 连接操作失败。</span><span class="sxs-lookup"><span data-stu-id="3cdf9-103">The TCP connect operation failed.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3cdf9-104">描述</span><span class="sxs-lookup"><span data-stu-id="3cdf9-104">Description</span></span>  
 <span data-ttu-id="3cdf9-105">此警告级别的跟踪指示未能连接到 TCP 终结点。</span><span class="sxs-lookup"><span data-stu-id="3cdf9-105">This warning level trace indicates a failure to connect to a TCP endpoint.</span></span> <span data-ttu-id="3cdf9-106">如果远程终结点在给定 IP 地址和端口没有响应，则可能出现此情况。</span><span class="sxs-lookup"><span data-stu-id="3cdf9-106">This could happen if the remote endpoint is not responding at a given IP address and port.</span></span> <span data-ttu-id="3cdf9-107">如果随后进行的连接到其他有效 IP 地址（如 IPv4 或 IPv6 地址，或表示给定主机名的其他 IP 地址）的尝试成功，则可以忽略此跟踪。</span><span class="sxs-lookup"><span data-stu-id="3cdf9-107">This trace can be ignored if subsequent attempts to connect to other valid IP addresses (such as IPv4 or IPv6 addresses, or other IP addresses representing a given hostname) succeed.</span></span> <span data-ttu-id="3cdf9-108">此跟踪内的异常可披露与错误有关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="3cdf9-108">The exception within this trace can reveal additional information about the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdf9-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cdf9-109">See also</span></span>

- [<span data-ttu-id="3cdf9-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="3cdf9-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3cdf9-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="3cdf9-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3cdf9-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="3cdf9-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
