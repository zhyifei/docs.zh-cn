---
title: 1027 - StartTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6545159012519e2943556b093a0a0bfc3e535217
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="4952a-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="4952a-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4952a-103">属性</span><span class="sxs-lookup"><span data-stu-id="4952a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4952a-104">ID</span><span class="sxs-lookup"><span data-stu-id="4952a-104">ID</span></span>|<span data-ttu-id="4952a-105">1027</span><span class="sxs-lookup"><span data-stu-id="4952a-105">1027</span></span>|  
|<span data-ttu-id="4952a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4952a-106">Keywords</span></span>|<span data-ttu-id="4952a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4952a-107">WFRuntime</span></span>|  
|<span data-ttu-id="4952a-108">级别</span><span class="sxs-lookup"><span data-stu-id="4952a-108">Level</span></span>|<span data-ttu-id="4952a-109">详细</span><span class="sxs-lookup"><span data-stu-id="4952a-109">Verbose</span></span>|  
|<span data-ttu-id="4952a-110">通道</span><span class="sxs-lookup"><span data-stu-id="4952a-110">Channel</span></span>|<span data-ttu-id="4952a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4952a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4952a-112">描述</span><span class="sxs-lookup"><span data-stu-id="4952a-112">Description</span></span>  
 <span data-ttu-id="4952a-113">指示 TransactionContextWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="4952a-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4952a-114">消息</span><span class="sxs-lookup"><span data-stu-id="4952a-114">Message</span></span>  
 <span data-ttu-id="4952a-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="4952a-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4952a-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4952a-116">Details</span></span>  
  
|<span data-ttu-id="4952a-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4952a-117">Data Item Name</span></span>|<span data-ttu-id="4952a-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4952a-118">Data Item Type</span></span>|<span data-ttu-id="4952a-119">描述</span><span class="sxs-lookup"><span data-stu-id="4952a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4952a-120">Activity</span><span class="sxs-lookup"><span data-stu-id="4952a-120">Activity</span></span>|<span data-ttu-id="4952a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4952a-121">xs:string</span></span>|<span data-ttu-id="4952a-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="4952a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4952a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4952a-123">DisplayName</span></span>|<span data-ttu-id="4952a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4952a-124">xs:string</span></span>|<span data-ttu-id="4952a-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4952a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4952a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4952a-126">InstanceId</span></span>|<span data-ttu-id="4952a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4952a-127">xs:string</span></span>|<span data-ttu-id="4952a-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="4952a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4952a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4952a-129">AppDomain</span></span>|<span data-ttu-id="4952a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4952a-130">xs:string</span></span>|<span data-ttu-id="4952a-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4952a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
