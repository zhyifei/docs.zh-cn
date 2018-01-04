---
title: 1028 - CompleteTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3cd2ee443d6c521f168a170a1079eb4e9657e2dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="d697d-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="d697d-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d697d-103">属性</span><span class="sxs-lookup"><span data-stu-id="d697d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d697d-104">ID</span><span class="sxs-lookup"><span data-stu-id="d697d-104">ID</span></span>|<span data-ttu-id="d697d-105">1028</span><span class="sxs-lookup"><span data-stu-id="d697d-105">1028</span></span>|  
|<span data-ttu-id="d697d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d697d-106">Keywords</span></span>|<span data-ttu-id="d697d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d697d-107">WFRuntime</span></span>|  
|<span data-ttu-id="d697d-108">级别</span><span class="sxs-lookup"><span data-stu-id="d697d-108">Level</span></span>|<span data-ttu-id="d697d-109">详细</span><span class="sxs-lookup"><span data-stu-id="d697d-109">Verbose</span></span>|  
|<span data-ttu-id="d697d-110">通道</span><span class="sxs-lookup"><span data-stu-id="d697d-110">Channel</span></span>|<span data-ttu-id="d697d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d697d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d697d-112">描述</span><span class="sxs-lookup"><span data-stu-id="d697d-112">Description</span></span>  
 <span data-ttu-id="d697d-113">指示 TransactionContextWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="d697d-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d697d-114">消息</span><span class="sxs-lookup"><span data-stu-id="d697d-114">Message</span></span>  
 <span data-ttu-id="d697d-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 TransactionContextWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="d697d-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d697d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d697d-116">Details</span></span>  
  
|<span data-ttu-id="d697d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d697d-117">Data Item Name</span></span>|<span data-ttu-id="d697d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d697d-118">Data Item Type</span></span>|<span data-ttu-id="d697d-119">描述</span><span class="sxs-lookup"><span data-stu-id="d697d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d697d-120">Activity</span><span class="sxs-lookup"><span data-stu-id="d697d-120">Activity</span></span>|<span data-ttu-id="d697d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d697d-121">xs:string</span></span>|<span data-ttu-id="d697d-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="d697d-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d697d-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d697d-123">DisplayName</span></span>|<span data-ttu-id="d697d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d697d-124">xs:string</span></span>|<span data-ttu-id="d697d-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d697d-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d697d-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d697d-126">InstanceId</span></span>|<span data-ttu-id="d697d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d697d-127">xs:string</span></span>|<span data-ttu-id="d697d-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="d697d-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d697d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d697d-129">AppDomain</span></span>|<span data-ttu-id="d697d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d697d-130">xs:string</span></span>|<span data-ttu-id="d697d-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d697d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
