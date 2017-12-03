---
title: 4211 - QueuingSqlRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 349a91f5b4708d829aee8d7f055871ac7dcc8914
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="6fad0-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="6fad0-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="6fad0-103">属性</span><span class="sxs-lookup"><span data-stu-id="6fad0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6fad0-104">ID</span><span class="sxs-lookup"><span data-stu-id="6fad0-104">ID</span></span>|<span data-ttu-id="6fad0-105">4211</span><span class="sxs-lookup"><span data-stu-id="6fad0-105">4211</span></span>|  
|<span data-ttu-id="6fad0-106">关键字</span><span class="sxs-lookup"><span data-stu-id="6fad0-106">Keywords</span></span>|<span data-ttu-id="6fad0-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="6fad0-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="6fad0-108">级别</span><span class="sxs-lookup"><span data-stu-id="6fad0-108">Level</span></span>|<span data-ttu-id="6fad0-109">警告</span><span class="sxs-lookup"><span data-stu-id="6fad0-109">Warning</span></span>|  
|<span data-ttu-id="6fad0-110">通道</span><span class="sxs-lookup"><span data-stu-id="6fad0-110">Channel</span></span>|<span data-ttu-id="6fad0-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="6fad0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6fad0-112">描述</span><span class="sxs-lookup"><span data-stu-id="6fad0-112">Description</span></span>  
 <span data-ttu-id="6fad0-113">指示将 SQL 重试排队。</span><span class="sxs-lookup"><span data-stu-id="6fad0-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6fad0-114">消息</span><span class="sxs-lookup"><span data-stu-id="6fad0-114">Message</span></span>  
 <span data-ttu-id="6fad0-115">正在将 SQL 重试排队，延迟 %1 毫秒。</span><span class="sxs-lookup"><span data-stu-id="6fad0-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6fad0-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="6fad0-116">Details</span></span>  
  
|<span data-ttu-id="6fad0-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="6fad0-117">Data Item Name</span></span>|<span data-ttu-id="6fad0-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="6fad0-118">Data Item Type</span></span>|<span data-ttu-id="6fad0-119">描述</span><span class="sxs-lookup"><span data-stu-id="6fad0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6fad0-120">Delay</span><span class="sxs-lookup"><span data-stu-id="6fad0-120">Delay</span></span>|<span data-ttu-id="6fad0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6fad0-121">xs:string</span></span>|<span data-ttu-id="6fad0-122">两次重试之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="6fad0-122">The delay between retries.</span></span>|  
|<span data-ttu-id="6fad0-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6fad0-123">AppDomain</span></span>|<span data-ttu-id="6fad0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6fad0-124">xs:string</span></span>|<span data-ttu-id="6fad0-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="6fad0-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
