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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 934c2947e86b429e9b990c273f22c0511f209a53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="22135-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="22135-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="22135-103">属性</span><span class="sxs-lookup"><span data-stu-id="22135-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22135-104">ID</span><span class="sxs-lookup"><span data-stu-id="22135-104">ID</span></span>|<span data-ttu-id="22135-105">1125</span><span class="sxs-lookup"><span data-stu-id="22135-105">1125</span></span>|  
|<span data-ttu-id="22135-106">关键字</span><span class="sxs-lookup"><span data-stu-id="22135-106">Keywords</span></span>|<span data-ttu-id="22135-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="22135-107">WFRuntime</span></span>|  
|<span data-ttu-id="22135-108">级别</span><span class="sxs-lookup"><span data-stu-id="22135-108">Level</span></span>|<span data-ttu-id="22135-109">信息</span><span class="sxs-lookup"><span data-stu-id="22135-109">Information</span></span>|  
|<span data-ttu-id="22135-110">通道</span><span class="sxs-lookup"><span data-stu-id="22135-110">Channel</span></span>|<span data-ttu-id="22135-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="22135-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="22135-112">描述</span><span class="sxs-lookup"><span data-stu-id="22135-112">Description</span></span>  
 <span data-ttu-id="22135-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是非静态的。</span><span class="sxs-lookup"><span data-stu-id="22135-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="22135-114">消息</span><span class="sxs-lookup"><span data-stu-id="22135-114">Message</span></span>  
 <span data-ttu-id="22135-115">InvokeMethod“%1”- 方法非静态。</span><span class="sxs-lookup"><span data-stu-id="22135-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="22135-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="22135-116">Details</span></span>  
  
|<span data-ttu-id="22135-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="22135-117">Data Item Name</span></span>|<span data-ttu-id="22135-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="22135-118">Data Item Type</span></span>|<span data-ttu-id="22135-119">描述</span><span class="sxs-lookup"><span data-stu-id="22135-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="22135-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="22135-120">InvokeMethod</span></span>|<span data-ttu-id="22135-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="22135-121">xs:string</span></span>|<span data-ttu-id="22135-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="22135-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="22135-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="22135-123">AppDomain</span></span>|<span data-ttu-id="22135-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="22135-124">xs:string</span></span>|<span data-ttu-id="22135-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="22135-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
