---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf90e78ed7fbfe500ac52e6629d31bd0aff97bd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="d4b63-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="d4b63-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="d4b63-103">属性</span><span class="sxs-lookup"><span data-stu-id="d4b63-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4b63-104">ID</span><span class="sxs-lookup"><span data-stu-id="d4b63-104">ID</span></span>|<span data-ttu-id="d4b63-105">3552</span><span class="sxs-lookup"><span data-stu-id="d4b63-105">3552</span></span>|  
|<span data-ttu-id="d4b63-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d4b63-106">Keywords</span></span>|<span data-ttu-id="d4b63-107">配额、WFServices</span><span class="sxs-lookup"><span data-stu-id="d4b63-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="d4b63-108">级别</span><span class="sxs-lookup"><span data-stu-id="d4b63-108">Level</span></span>|<span data-ttu-id="d4b63-109">警告</span><span class="sxs-lookup"><span data-stu-id="d4b63-109">Warning</span></span>|  
|<span data-ttu-id="d4b63-110">通道</span><span class="sxs-lookup"><span data-stu-id="d4b63-110">Channel</span></span>|<span data-ttu-id="d4b63-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="d4b63-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4b63-112">描述</span><span class="sxs-lookup"><span data-stu-id="d4b63-112">Description</span></span>  
 <span data-ttu-id="d4b63-113">指示达到了中止值“MaxPendingMessagesPerChannel”。</span><span class="sxs-lookup"><span data-stu-id="d4b63-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4b63-114">消息</span><span class="sxs-lookup"><span data-stu-id="d4b63-114">Message</span></span>  
 <span data-ttu-id="d4b63-115">已达到了中止值 maxpendingmessagesperchannel 的"%1"。</span><span class="sxs-lookup"><span data-stu-id="d4b63-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="d4b63-116">若要增加此限制，请调整 BufferedReceiveServiceBehavior 中的 MaxPendingMessagesPerChannel 属性。</span><span class="sxs-lookup"><span data-stu-id="d4b63-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4b63-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="d4b63-117">Details</span></span>  
  
|<span data-ttu-id="d4b63-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d4b63-118">Data Item Name</span></span>|<span data-ttu-id="d4b63-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d4b63-119">Data Item Type</span></span>|<span data-ttu-id="d4b63-120">描述</span><span class="sxs-lookup"><span data-stu-id="d4b63-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4b63-121">限制值</span><span class="sxs-lookup"><span data-stu-id="d4b63-121">Limit</span></span>|<span data-ttu-id="d4b63-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4b63-122">xs:string</span></span>|<span data-ttu-id="d4b63-123">中止值 MaxPendingMessagesPerChannel。</span><span class="sxs-lookup"><span data-stu-id="d4b63-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="d4b63-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4b63-124">AppDomain</span></span>|<span data-ttu-id="d4b63-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4b63-125">xs:string</span></span>|<span data-ttu-id="d4b63-126">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d4b63-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
