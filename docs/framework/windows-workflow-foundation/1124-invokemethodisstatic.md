---
title: 1124 - InvokeMethodIsStatic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4fbeeb37813d4e387fc976b50f22809f7ead8926
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1124---invokemethodisstatic"></a><span data-ttu-id="2a4dd-102">1124 - InvokeMethodIsStatic</span><span class="sxs-lookup"><span data-stu-id="2a4dd-102">1124 - InvokeMethodIsStatic</span></span>
## <a name="properties"></a><span data-ttu-id="2a4dd-103">属性</span><span class="sxs-lookup"><span data-stu-id="2a4dd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a4dd-104">ID</span><span class="sxs-lookup"><span data-stu-id="2a4dd-104">ID</span></span>|<span data-ttu-id="2a4dd-105">1124</span><span class="sxs-lookup"><span data-stu-id="2a4dd-105">1124</span></span>|  
|<span data-ttu-id="2a4dd-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2a4dd-106">Keywords</span></span>|<span data-ttu-id="2a4dd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2a4dd-107">WFRuntime</span></span>|  
|<span data-ttu-id="2a4dd-108">级别</span><span class="sxs-lookup"><span data-stu-id="2a4dd-108">Level</span></span>|<span data-ttu-id="2a4dd-109">信息</span><span class="sxs-lookup"><span data-stu-id="2a4dd-109">Information</span></span>|  
|<span data-ttu-id="2a4dd-110">通道</span><span class="sxs-lookup"><span data-stu-id="2a4dd-110">Channel</span></span>|<span data-ttu-id="2a4dd-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="2a4dd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a4dd-112">描述</span><span class="sxs-lookup"><span data-stu-id="2a4dd-112">Description</span></span>  
 <span data-ttu-id="2a4dd-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是静态的。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a4dd-114">消息</span><span class="sxs-lookup"><span data-stu-id="2a4dd-114">Message</span></span>  
 <span data-ttu-id="2a4dd-115">InvokeMethod“%1”- 方法为静态。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-115">InvokeMethod '%1' - method is Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a4dd-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a4dd-116">Details</span></span>  
  
|<span data-ttu-id="2a4dd-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2a4dd-117">Data Item Name</span></span>|<span data-ttu-id="2a4dd-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2a4dd-118">Data Item Type</span></span>|<span data-ttu-id="2a4dd-119">描述</span><span class="sxs-lookup"><span data-stu-id="2a4dd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a4dd-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="2a4dd-120">InvokeMethod</span></span>|<span data-ttu-id="2a4dd-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a4dd-121">xs:string</span></span>|<span data-ttu-id="2a4dd-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="2a4dd-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2a4dd-123">AppDomain</span></span>|<span data-ttu-id="2a4dd-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a4dd-124">xs:string</span></span>|<span data-ttu-id="2a4dd-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2a4dd-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
