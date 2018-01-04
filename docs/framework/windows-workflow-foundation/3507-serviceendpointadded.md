---
title: 3507 - ServiceEndpointAdded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f06e6cccd9c4ca2907b86372f609f8c72b5e189
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="8cb5e-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="8cb5e-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="8cb5e-103">属性</span><span class="sxs-lookup"><span data-stu-id="8cb5e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cb5e-104">ID</span><span class="sxs-lookup"><span data-stu-id="8cb5e-104">ID</span></span>|<span data-ttu-id="8cb5e-105">3507</span><span class="sxs-lookup"><span data-stu-id="8cb5e-105">3507</span></span>|  
|<span data-ttu-id="8cb5e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8cb5e-106">Keywords</span></span>|<span data-ttu-id="8cb5e-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="8cb5e-107">WFServices</span></span>|  
|<span data-ttu-id="8cb5e-108">级别</span><span class="sxs-lookup"><span data-stu-id="8cb5e-108">Level</span></span>|<span data-ttu-id="8cb5e-109">信息</span><span class="sxs-lookup"><span data-stu-id="8cb5e-109">Information</span></span>|  
|<span data-ttu-id="8cb5e-110">通道</span><span class="sxs-lookup"><span data-stu-id="8cb5e-110">Channel</span></span>|<span data-ttu-id="8cb5e-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="8cb5e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8cb5e-112">描述</span><span class="sxs-lookup"><span data-stu-id="8cb5e-112">Description</span></span>  
 <span data-ttu-id="8cb5e-113">指示添加了服务终结点。</span><span class="sxs-lookup"><span data-stu-id="8cb5e-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8cb5e-114">消息</span><span class="sxs-lookup"><span data-stu-id="8cb5e-114">Message</span></span>  
 <span data-ttu-id="8cb5e-115">已为地址“%1”、绑定“%2”和协定“%3”添加了服务终结点。</span><span class="sxs-lookup"><span data-stu-id="8cb5e-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8cb5e-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="8cb5e-116">Details</span></span>  
  
|<span data-ttu-id="8cb5e-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8cb5e-117">Data Item Name</span></span>|<span data-ttu-id="8cb5e-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8cb5e-118">Data Item Type</span></span>|<span data-ttu-id="8cb5e-119">描述</span><span class="sxs-lookup"><span data-stu-id="8cb5e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8cb5e-120">Address</span><span class="sxs-lookup"><span data-stu-id="8cb5e-120">Address</span></span>|<span data-ttu-id="8cb5e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cb5e-121">xs:string</span></span>|<span data-ttu-id="8cb5e-122">终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="8cb5e-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="8cb5e-123">绑定</span><span class="sxs-lookup"><span data-stu-id="8cb5e-123">Binding</span></span>|<span data-ttu-id="8cb5e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cb5e-124">xs:string</span></span>|<span data-ttu-id="8cb5e-125">终结点的绑定。</span><span class="sxs-lookup"><span data-stu-id="8cb5e-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="8cb5e-126">协定</span><span class="sxs-lookup"><span data-stu-id="8cb5e-126">Contract</span></span>|<span data-ttu-id="8cb5e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cb5e-127">xs:string</span></span>|<span data-ttu-id="8cb5e-128">终结点的协定。</span><span class="sxs-lookup"><span data-stu-id="8cb5e-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="8cb5e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8cb5e-129">AppDomain</span></span>|<span data-ttu-id="8cb5e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cb5e-130">xs:string</span></span>|<span data-ttu-id="8cb5e-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8cb5e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
