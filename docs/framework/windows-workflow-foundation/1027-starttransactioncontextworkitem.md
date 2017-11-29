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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be35a4d478f4f2af0921cac942ebb95d6aed38d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="63bfa-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="63bfa-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="63bfa-103">属性</span><span class="sxs-lookup"><span data-stu-id="63bfa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63bfa-104">ID</span><span class="sxs-lookup"><span data-stu-id="63bfa-104">ID</span></span>|<span data-ttu-id="63bfa-105">1027</span><span class="sxs-lookup"><span data-stu-id="63bfa-105">1027</span></span>|  
|<span data-ttu-id="63bfa-106">关键字</span><span class="sxs-lookup"><span data-stu-id="63bfa-106">Keywords</span></span>|<span data-ttu-id="63bfa-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="63bfa-107">WFRuntime</span></span>|  
|<span data-ttu-id="63bfa-108">级别</span><span class="sxs-lookup"><span data-stu-id="63bfa-108">Level</span></span>|<span data-ttu-id="63bfa-109">详细</span><span class="sxs-lookup"><span data-stu-id="63bfa-109">Verbose</span></span>|  
|<span data-ttu-id="63bfa-110">通道</span><span class="sxs-lookup"><span data-stu-id="63bfa-110">Channel</span></span>|<span data-ttu-id="63bfa-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="63bfa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="63bfa-112">描述</span><span class="sxs-lookup"><span data-stu-id="63bfa-112">Description</span></span>  
 <span data-ttu-id="63bfa-113">指示 TransactionContextWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="63bfa-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="63bfa-114">消息</span><span class="sxs-lookup"><span data-stu-id="63bfa-114">Message</span></span>  
 <span data-ttu-id="63bfa-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="63bfa-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="63bfa-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="63bfa-116">Details</span></span>  
  
|<span data-ttu-id="63bfa-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="63bfa-117">Data Item Name</span></span>|<span data-ttu-id="63bfa-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="63bfa-118">Data Item Type</span></span>|<span data-ttu-id="63bfa-119">描述</span><span class="sxs-lookup"><span data-stu-id="63bfa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="63bfa-120">Activity</span><span class="sxs-lookup"><span data-stu-id="63bfa-120">Activity</span></span>|<span data-ttu-id="63bfa-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="63bfa-121">xs:string</span></span>|<span data-ttu-id="63bfa-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="63bfa-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="63bfa-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="63bfa-123">DisplayName</span></span>|<span data-ttu-id="63bfa-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="63bfa-124">xs:string</span></span>|<span data-ttu-id="63bfa-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="63bfa-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="63bfa-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="63bfa-126">InstanceId</span></span>|<span data-ttu-id="63bfa-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="63bfa-127">xs:string</span></span>|<span data-ttu-id="63bfa-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="63bfa-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="63bfa-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="63bfa-129">AppDomain</span></span>|<span data-ttu-id="63bfa-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="63bfa-130">xs:string</span></span>|<span data-ttu-id="63bfa-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="63bfa-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
