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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f9f8f4e836d5c5b437edcfaff6460c7b97210ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="22cbe-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="22cbe-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="22cbe-103">属性</span><span class="sxs-lookup"><span data-stu-id="22cbe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22cbe-104">ID</span><span class="sxs-lookup"><span data-stu-id="22cbe-104">ID</span></span>|<span data-ttu-id="22cbe-105">1131</span><span class="sxs-lookup"><span data-stu-id="22cbe-105">1131</span></span>|  
|<span data-ttu-id="22cbe-106">关键字</span><span class="sxs-lookup"><span data-stu-id="22cbe-106">Keywords</span></span>|<span data-ttu-id="22cbe-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="22cbe-107">WFRuntime</span></span>|  
|<span data-ttu-id="22cbe-108">级别</span><span class="sxs-lookup"><span data-stu-id="22cbe-108">Level</span></span>|<span data-ttu-id="22cbe-109">信息</span><span class="sxs-lookup"><span data-stu-id="22cbe-109">Information</span></span>|  
|<span data-ttu-id="22cbe-110">通道</span><span class="sxs-lookup"><span data-stu-id="22cbe-110">Channel</span></span>|<span data-ttu-id="22cbe-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="22cbe-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="22cbe-112">描述</span><span class="sxs-lookup"><span data-stu-id="22cbe-112">Description</span></span>  
 <span data-ttu-id="22cbe-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="22cbe-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="22cbe-114">消息</span><span class="sxs-lookup"><span data-stu-id="22cbe-114">Message</span></span>  
 <span data-ttu-id="22cbe-115">InvokeMethod“%1”- 方法使用“%2”和“%3”的异步模式。</span><span class="sxs-lookup"><span data-stu-id="22cbe-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="22cbe-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="22cbe-116">Details</span></span>  
  
|<span data-ttu-id="22cbe-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="22cbe-117">Data Item Name</span></span>|<span data-ttu-id="22cbe-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="22cbe-118">Data Item Type</span></span>|<span data-ttu-id="22cbe-119">描述</span><span class="sxs-lookup"><span data-stu-id="22cbe-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="22cbe-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="22cbe-120">InvokeMethod</span></span>|<span data-ttu-id="22cbe-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="22cbe-121">xs:string</span></span>|<span data-ttu-id="22cbe-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="22cbe-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="22cbe-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="22cbe-123">BeginMethod</span></span>|<span data-ttu-id="22cbe-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="22cbe-124">xs:string</span></span>|<span data-ttu-id="22cbe-125">begin 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="22cbe-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="22cbe-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="22cbe-126">EndMethod</span></span>|<span data-ttu-id="22cbe-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="22cbe-127">xs:string</span></span>|<span data-ttu-id="22cbe-128">end 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="22cbe-128">The name of the end method.</span></span>|  
|<span data-ttu-id="22cbe-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="22cbe-129">AppDomain</span></span>|<span data-ttu-id="22cbe-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="22cbe-130">xs:string</span></span>|<span data-ttu-id="22cbe-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="22cbe-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
