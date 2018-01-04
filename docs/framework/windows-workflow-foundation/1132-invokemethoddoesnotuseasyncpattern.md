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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75386b56f7926b9ddb883e0ca212d795898fe6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="976bf-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="976bf-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="976bf-103">属性</span><span class="sxs-lookup"><span data-stu-id="976bf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="976bf-104">ID</span><span class="sxs-lookup"><span data-stu-id="976bf-104">ID</span></span>|<span data-ttu-id="976bf-105">1132</span><span class="sxs-lookup"><span data-stu-id="976bf-105">1132</span></span>|  
|<span data-ttu-id="976bf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="976bf-106">Keywords</span></span>|<span data-ttu-id="976bf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="976bf-107">WFRuntime</span></span>|  
|<span data-ttu-id="976bf-108">级别</span><span class="sxs-lookup"><span data-stu-id="976bf-108">Level</span></span>|<span data-ttu-id="976bf-109">信息</span><span class="sxs-lookup"><span data-stu-id="976bf-109">Information</span></span>|  
|<span data-ttu-id="976bf-110">通道</span><span class="sxs-lookup"><span data-stu-id="976bf-110">Channel</span></span>|<span data-ttu-id="976bf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="976bf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="976bf-112">描述</span><span class="sxs-lookup"><span data-stu-id="976bf-112">Description</span></span>  
 <span data-ttu-id="976bf-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时未使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="976bf-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="976bf-114">消息</span><span class="sxs-lookup"><span data-stu-id="976bf-114">Message</span></span>  
 <span data-ttu-id="976bf-115">InvokeMethod“%1”- 方法不使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="976bf-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="976bf-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="976bf-116">Details</span></span>  
  
|<span data-ttu-id="976bf-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="976bf-117">Data Item Name</span></span>|<span data-ttu-id="976bf-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="976bf-118">Data Item Type</span></span>|<span data-ttu-id="976bf-119">描述</span><span class="sxs-lookup"><span data-stu-id="976bf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="976bf-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="976bf-120">InvokeMethod</span></span>|<span data-ttu-id="976bf-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="976bf-121">xs:string</span></span>|<span data-ttu-id="976bf-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="976bf-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="976bf-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="976bf-123">AppDomain</span></span>|<span data-ttu-id="976bf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="976bf-124">xs:string</span></span>|<span data-ttu-id="976bf-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="976bf-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
