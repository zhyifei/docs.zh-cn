---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: 4c352ad4ac4ffee5d12c054590ef994bab0ba757
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642576"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="23103-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="23103-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="23103-103">PeerMaintainer 模块正在执行特定操作（详细信息包含在跟踪消息正文中）。</span><span class="sxs-lookup"><span data-stu-id="23103-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="23103-104">描述</span><span class="sxs-lookup"><span data-stu-id="23103-104">Description</span></span>  
 <span data-ttu-id="23103-105">此跟踪在各种 PeerMaintainer 操作期间发生。</span><span class="sxs-lookup"><span data-stu-id="23103-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="23103-106">PeerMaintainer 是 PeerNode 的内部组件。</span><span class="sxs-lookup"><span data-stu-id="23103-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="23103-107">每隔一分钟，或者每当接收到 32 条消息，该组件就向它的邻居发送一条 LinkUtility 消息，该消息中包含有关交换了多少条消息以及其中有多少条有用消息（不重复也未经篡改的消息）的统计信息。</span><span class="sxs-lookup"><span data-stu-id="23103-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="23103-108">这有助于确定特定邻居的链接利用率。</span><span class="sxs-lookup"><span data-stu-id="23103-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="23103-109">该维护组件大约每五分钟检查一次邻居连接的运行状况。</span><span class="sxs-lookup"><span data-stu-id="23103-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="23103-110">如果邻居连接的数目超过理想的数值，该维护组件将去除用处最小的一些连接。</span><span class="sxs-lookup"><span data-stu-id="23103-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="23103-111">如果连接数目不足，该维护组件将获取新的连接。</span><span class="sxs-lookup"><span data-stu-id="23103-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23103-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="23103-112">See also</span></span>
- [<span data-ttu-id="23103-113">跟踪</span><span class="sxs-lookup"><span data-stu-id="23103-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="23103-114">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="23103-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="23103-115">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="23103-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
