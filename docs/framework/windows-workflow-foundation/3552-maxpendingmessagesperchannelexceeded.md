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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ba5e4aa8e1338321838e40db7d976107315ef64
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="6aa6c-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="6aa6c-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="6aa6c-103">属性</span><span class="sxs-lookup"><span data-stu-id="6aa6c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6aa6c-104">ID</span><span class="sxs-lookup"><span data-stu-id="6aa6c-104">ID</span></span>|<span data-ttu-id="6aa6c-105">3552</span><span class="sxs-lookup"><span data-stu-id="6aa6c-105">3552</span></span>|  
|<span data-ttu-id="6aa6c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="6aa6c-106">Keywords</span></span>|<span data-ttu-id="6aa6c-107">配额、WFServices</span><span class="sxs-lookup"><span data-stu-id="6aa6c-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="6aa6c-108">级别</span><span class="sxs-lookup"><span data-stu-id="6aa6c-108">Level</span></span>|<span data-ttu-id="6aa6c-109">警告</span><span class="sxs-lookup"><span data-stu-id="6aa6c-109">Warning</span></span>|  
|<span data-ttu-id="6aa6c-110">通道</span><span class="sxs-lookup"><span data-stu-id="6aa6c-110">Channel</span></span>|<span data-ttu-id="6aa6c-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="6aa6c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6aa6c-112">描述</span><span class="sxs-lookup"><span data-stu-id="6aa6c-112">Description</span></span>  
 <span data-ttu-id="6aa6c-113">指示达到了中止值“MaxPendingMessagesPerChannel”。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6aa6c-114">消息</span><span class="sxs-lookup"><span data-stu-id="6aa6c-114">Message</span></span>  
 <span data-ttu-id="6aa6c-115">已达到了中止值 maxpendingmessagesperchannel 的"%1"。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="6aa6c-116">若要增加此限制，请调整 BufferedReceiveServiceBehavior 中的 MaxPendingMessagesPerChannel 属性。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6aa6c-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="6aa6c-117">Details</span></span>  
  
|<span data-ttu-id="6aa6c-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="6aa6c-118">Data Item Name</span></span>|<span data-ttu-id="6aa6c-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="6aa6c-119">Data Item Type</span></span>|<span data-ttu-id="6aa6c-120">描述</span><span class="sxs-lookup"><span data-stu-id="6aa6c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6aa6c-121">限制值</span><span class="sxs-lookup"><span data-stu-id="6aa6c-121">Limit</span></span>|<span data-ttu-id="6aa6c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6aa6c-122">xs:string</span></span>|<span data-ttu-id="6aa6c-123">中止值 MaxPendingMessagesPerChannel。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="6aa6c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6aa6c-124">AppDomain</span></span>|<span data-ttu-id="6aa6c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6aa6c-125">xs:string</span></span>|<span data-ttu-id="6aa6c-126">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
