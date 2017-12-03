---
title: 1125 - InvokeMethodIsNotStatic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b31bb8db8252474d20f7523e08cadf35bfcc84a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="ef52c-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="ef52c-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="ef52c-103">属性</span><span class="sxs-lookup"><span data-stu-id="ef52c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef52c-104">ID</span><span class="sxs-lookup"><span data-stu-id="ef52c-104">ID</span></span>|<span data-ttu-id="ef52c-105">1125</span><span class="sxs-lookup"><span data-stu-id="ef52c-105">1125</span></span>|  
|<span data-ttu-id="ef52c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ef52c-106">Keywords</span></span>|<span data-ttu-id="ef52c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ef52c-107">WFRuntime</span></span>|  
|<span data-ttu-id="ef52c-108">级别</span><span class="sxs-lookup"><span data-stu-id="ef52c-108">Level</span></span>|<span data-ttu-id="ef52c-109">信息</span><span class="sxs-lookup"><span data-stu-id="ef52c-109">Information</span></span>|  
|<span data-ttu-id="ef52c-110">通道</span><span class="sxs-lookup"><span data-stu-id="ef52c-110">Channel</span></span>|<span data-ttu-id="ef52c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="ef52c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ef52c-112">描述</span><span class="sxs-lookup"><span data-stu-id="ef52c-112">Description</span></span>  
 <span data-ttu-id="ef52c-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是非静态的。</span><span class="sxs-lookup"><span data-stu-id="ef52c-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ef52c-114">消息</span><span class="sxs-lookup"><span data-stu-id="ef52c-114">Message</span></span>  
 <span data-ttu-id="ef52c-115">InvokeMethod“%1”- 方法非静态。</span><span class="sxs-lookup"><span data-stu-id="ef52c-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ef52c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef52c-116">Details</span></span>  
  
|<span data-ttu-id="ef52c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ef52c-117">Data Item Name</span></span>|<span data-ttu-id="ef52c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ef52c-118">Data Item Type</span></span>|<span data-ttu-id="ef52c-119">描述</span><span class="sxs-lookup"><span data-stu-id="ef52c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ef52c-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="ef52c-120">InvokeMethod</span></span>|<span data-ttu-id="ef52c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef52c-121">xs:string</span></span>|<span data-ttu-id="ef52c-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ef52c-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="ef52c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ef52c-123">AppDomain</span></span>|<span data-ttu-id="ef52c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef52c-124">xs:string</span></span>|<span data-ttu-id="ef52c-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ef52c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
