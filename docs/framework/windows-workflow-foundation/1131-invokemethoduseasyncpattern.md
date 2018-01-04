---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 739357df85ceb73e246adcb2b09f88d270d853ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="9441d-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="9441d-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="9441d-103">属性</span><span class="sxs-lookup"><span data-stu-id="9441d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9441d-104">ID</span><span class="sxs-lookup"><span data-stu-id="9441d-104">ID</span></span>|<span data-ttu-id="9441d-105">1131</span><span class="sxs-lookup"><span data-stu-id="9441d-105">1131</span></span>|  
|<span data-ttu-id="9441d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9441d-106">Keywords</span></span>|<span data-ttu-id="9441d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9441d-107">WFRuntime</span></span>|  
|<span data-ttu-id="9441d-108">级别</span><span class="sxs-lookup"><span data-stu-id="9441d-108">Level</span></span>|<span data-ttu-id="9441d-109">信息</span><span class="sxs-lookup"><span data-stu-id="9441d-109">Information</span></span>|  
|<span data-ttu-id="9441d-110">通道</span><span class="sxs-lookup"><span data-stu-id="9441d-110">Channel</span></span>|<span data-ttu-id="9441d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9441d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9441d-112">描述</span><span class="sxs-lookup"><span data-stu-id="9441d-112">Description</span></span>  
 <span data-ttu-id="9441d-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="9441d-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9441d-114">消息</span><span class="sxs-lookup"><span data-stu-id="9441d-114">Message</span></span>  
 <span data-ttu-id="9441d-115">InvokeMethod“%1”- 方法使用“%2”和“%3”的异步模式。</span><span class="sxs-lookup"><span data-stu-id="9441d-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9441d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9441d-116">Details</span></span>  
  
|<span data-ttu-id="9441d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9441d-117">Data Item Name</span></span>|<span data-ttu-id="9441d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9441d-118">Data Item Type</span></span>|<span data-ttu-id="9441d-119">描述</span><span class="sxs-lookup"><span data-stu-id="9441d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9441d-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="9441d-120">InvokeMethod</span></span>|<span data-ttu-id="9441d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9441d-121">xs:string</span></span>|<span data-ttu-id="9441d-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9441d-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="9441d-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="9441d-123">BeginMethod</span></span>|<span data-ttu-id="9441d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9441d-124">xs:string</span></span>|<span data-ttu-id="9441d-125">begin 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="9441d-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="9441d-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="9441d-126">EndMethod</span></span>|<span data-ttu-id="9441d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9441d-127">xs:string</span></span>|<span data-ttu-id="9441d-128">end 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="9441d-128">The name of the end method.</span></span>|  
|<span data-ttu-id="9441d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9441d-129">AppDomain</span></span>|<span data-ttu-id="9441d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9441d-130">xs:string</span></span>|<span data-ttu-id="9441d-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9441d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
