---
title: 440 - StartSignpostEvent1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b7772bcd8d637b14e3f91feceaccc9f045f390c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="367e2-102">440 - StartSignpostEvent1</span><span class="sxs-lookup"><span data-stu-id="367e2-102">440 - StartSignpostEvent1</span></span>
## <a name="properties"></a><span data-ttu-id="367e2-103">属性</span><span class="sxs-lookup"><span data-stu-id="367e2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="367e2-104">ID</span><span class="sxs-lookup"><span data-stu-id="367e2-104">ID</span></span>|<span data-ttu-id="367e2-105">440</span><span class="sxs-lookup"><span data-stu-id="367e2-105">440</span></span>|  
|<span data-ttu-id="367e2-106">关键字</span><span class="sxs-lookup"><span data-stu-id="367e2-106">Keywords</span></span>|<span data-ttu-id="367e2-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="367e2-107">Troubleshooting</span></span>|  
|<span data-ttu-id="367e2-108">级别</span><span class="sxs-lookup"><span data-stu-id="367e2-108">Level</span></span>|<span data-ttu-id="367e2-109">信息</span><span class="sxs-lookup"><span data-stu-id="367e2-109">Information</span></span>|  
|<span data-ttu-id="367e2-110">通道</span><span class="sxs-lookup"><span data-stu-id="367e2-110">Channel</span></span>|<span data-ttu-id="367e2-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="367e2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="367e2-112">描述</span><span class="sxs-lookup"><span data-stu-id="367e2-112">Description</span></span>  
 <span data-ttu-id="367e2-113">在活动跟踪中，指示消息是否已开始跨越发送或接收中的活动边界。</span><span class="sxs-lookup"><span data-stu-id="367e2-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="367e2-114">消息</span><span class="sxs-lookup"><span data-stu-id="367e2-114">Message</span></span>  
 <span data-ttu-id="367e2-115">活动边界。</span><span class="sxs-lookup"><span data-stu-id="367e2-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="367e2-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="367e2-116">Details</span></span>  
  
|<span data-ttu-id="367e2-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="367e2-117">Data Item Name</span></span>|<span data-ttu-id="367e2-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="367e2-118">Data Item Type</span></span>|<span data-ttu-id="367e2-119">描述</span><span class="sxs-lookup"><span data-stu-id="367e2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="367e2-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="367e2-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="367e2-121">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="367e2-121">The name of the activity.</span></span>|  
|<span data-ttu-id="367e2-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="367e2-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="367e2-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="367e2-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
