---
title: 4817 - InnerChannelCreationFailed
ms.date: 03/30/2017
ms.assetid: c1a20619-beda-49b9-bb64-76b6a009c32b
ms.openlocfilehash: e9c99281e6abe27a8e59583102a712c9fa5a3854
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33469565"
---
# <a name="4817---innerchannelcreationfailed"></a><span data-ttu-id="c11c5-102">4817 - InnerChannelCreationFailed</span><span class="sxs-lookup"><span data-stu-id="c11c5-102">4817 - InnerChannelCreationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="c11c5-103">属性</span><span class="sxs-lookup"><span data-stu-id="c11c5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c11c5-104">ID</span><span class="sxs-lookup"><span data-stu-id="c11c5-104">ID</span></span>|<span data-ttu-id="c11c5-105">4817</span><span class="sxs-lookup"><span data-stu-id="c11c5-105">4817</span></span>|  
|<span data-ttu-id="c11c5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c11c5-106">Keywords</span></span>|<span data-ttu-id="c11c5-107">发现</span><span class="sxs-lookup"><span data-stu-id="c11c5-107">Discovery</span></span>|  
|<span data-ttu-id="c11c5-108">级别</span><span class="sxs-lookup"><span data-stu-id="c11c5-108">Level</span></span>|<span data-ttu-id="c11c5-109">警告</span><span class="sxs-lookup"><span data-stu-id="c11c5-109">Warning</span></span>|  
|<span data-ttu-id="c11c5-110">通道</span><span class="sxs-lookup"><span data-stu-id="c11c5-110">Channel</span></span>|<span data-ttu-id="c11c5-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c11c5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c11c5-112">描述</span><span class="sxs-lookup"><span data-stu-id="c11c5-112">Description</span></span>  
 <span data-ttu-id="c11c5-113">在 DiscoveryClientChannel 无法使用已发现终结点创建通道时，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="c11c5-113">This event is emitted when the DiscoveryClientChannel failed to create the channel with a discovered endpoint.</span></span> <span data-ttu-id="c11c5-114">DiscoveryClientChannel 现在将尝试使用下一个可用的已发现终结点。</span><span class="sxs-lookup"><span data-stu-id="c11c5-114">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c11c5-115">消息</span><span class="sxs-lookup"><span data-stu-id="c11c5-115">Message</span></span>  
 <span data-ttu-id="c11c5-116">DiscoveryClientChannel 无法使用 EndpointAddress 为“%1”和 Via 为“%2”的已发现终结点创建通道。</span><span class="sxs-lookup"><span data-stu-id="c11c5-116">The DiscoveryClientChannel failed to create the channel with a discovered endpoint with EndpointAddress='%1' and Via='%2'.</span></span> <span data-ttu-id="c11c5-117">DiscoveryClientChannel 现在将尝试使用下一个可用的已发现终结点。</span><span class="sxs-lookup"><span data-stu-id="c11c5-117">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c11c5-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="c11c5-118">Details</span></span>
