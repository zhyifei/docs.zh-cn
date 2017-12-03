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
ms.openlocfilehash: db529ed413d70165c7813e23ce8f164262c8e16b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="d2cff-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="d2cff-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="d2cff-103">属性</span><span class="sxs-lookup"><span data-stu-id="d2cff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2cff-104">ID</span><span class="sxs-lookup"><span data-stu-id="d2cff-104">ID</span></span>|<span data-ttu-id="d2cff-105">1131</span><span class="sxs-lookup"><span data-stu-id="d2cff-105">1131</span></span>|  
|<span data-ttu-id="d2cff-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d2cff-106">Keywords</span></span>|<span data-ttu-id="d2cff-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d2cff-107">WFRuntime</span></span>|  
|<span data-ttu-id="d2cff-108">级别</span><span class="sxs-lookup"><span data-stu-id="d2cff-108">Level</span></span>|<span data-ttu-id="d2cff-109">信息</span><span class="sxs-lookup"><span data-stu-id="d2cff-109">Information</span></span>|  
|<span data-ttu-id="d2cff-110">通道</span><span class="sxs-lookup"><span data-stu-id="d2cff-110">Channel</span></span>|<span data-ttu-id="d2cff-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d2cff-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d2cff-112">描述</span><span class="sxs-lookup"><span data-stu-id="d2cff-112">Description</span></span>  
 <span data-ttu-id="d2cff-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="d2cff-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d2cff-114">消息</span><span class="sxs-lookup"><span data-stu-id="d2cff-114">Message</span></span>  
 <span data-ttu-id="d2cff-115">InvokeMethod“%1”- 方法使用“%2”和“%3”的异步模式。</span><span class="sxs-lookup"><span data-stu-id="d2cff-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d2cff-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2cff-116">Details</span></span>  
  
|<span data-ttu-id="d2cff-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d2cff-117">Data Item Name</span></span>|<span data-ttu-id="d2cff-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d2cff-118">Data Item Type</span></span>|<span data-ttu-id="d2cff-119">描述</span><span class="sxs-lookup"><span data-stu-id="d2cff-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d2cff-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d2cff-120">InvokeMethod</span></span>|<span data-ttu-id="d2cff-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2cff-121">xs:string</span></span>|<span data-ttu-id="d2cff-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d2cff-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="d2cff-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="d2cff-123">BeginMethod</span></span>|<span data-ttu-id="d2cff-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2cff-124">xs:string</span></span>|<span data-ttu-id="d2cff-125">begin 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="d2cff-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="d2cff-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="d2cff-126">EndMethod</span></span>|<span data-ttu-id="d2cff-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2cff-127">xs:string</span></span>|<span data-ttu-id="d2cff-128">end 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="d2cff-128">The name of the end method.</span></span>|  
|<span data-ttu-id="d2cff-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d2cff-129">AppDomain</span></span>|<span data-ttu-id="d2cff-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2cff-130">xs:string</span></span>|<span data-ttu-id="d2cff-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2cff-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
