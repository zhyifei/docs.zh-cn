---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 300e843529bfc76df4193b46cd713ce0bd9cdbfd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="32afd-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="32afd-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="32afd-103">属性</span><span class="sxs-lookup"><span data-stu-id="32afd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32afd-104">ID</span><span class="sxs-lookup"><span data-stu-id="32afd-104">ID</span></span>|<span data-ttu-id="32afd-105">1132</span><span class="sxs-lookup"><span data-stu-id="32afd-105">1132</span></span>|  
|<span data-ttu-id="32afd-106">关键字</span><span class="sxs-lookup"><span data-stu-id="32afd-106">Keywords</span></span>|<span data-ttu-id="32afd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="32afd-107">WFRuntime</span></span>|  
|<span data-ttu-id="32afd-108">级别</span><span class="sxs-lookup"><span data-stu-id="32afd-108">Level</span></span>|<span data-ttu-id="32afd-109">信息</span><span class="sxs-lookup"><span data-stu-id="32afd-109">Information</span></span>|  
|<span data-ttu-id="32afd-110">通道</span><span class="sxs-lookup"><span data-stu-id="32afd-110">Channel</span></span>|<span data-ttu-id="32afd-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="32afd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="32afd-112">描述</span><span class="sxs-lookup"><span data-stu-id="32afd-112">Description</span></span>  
 <span data-ttu-id="32afd-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时未使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="32afd-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="32afd-114">消息</span><span class="sxs-lookup"><span data-stu-id="32afd-114">Message</span></span>  
 <span data-ttu-id="32afd-115">InvokeMethod“%1”- 方法不使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="32afd-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="32afd-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="32afd-116">Details</span></span>  
  
|<span data-ttu-id="32afd-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="32afd-117">Data Item Name</span></span>|<span data-ttu-id="32afd-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="32afd-118">Data Item Type</span></span>|<span data-ttu-id="32afd-119">描述</span><span class="sxs-lookup"><span data-stu-id="32afd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="32afd-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="32afd-120">InvokeMethod</span></span>|<span data-ttu-id="32afd-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="32afd-121">xs:string</span></span>|<span data-ttu-id="32afd-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="32afd-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="32afd-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="32afd-123">AppDomain</span></span>|<span data-ttu-id="32afd-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="32afd-124">xs:string</span></span>|<span data-ttu-id="32afd-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="32afd-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
