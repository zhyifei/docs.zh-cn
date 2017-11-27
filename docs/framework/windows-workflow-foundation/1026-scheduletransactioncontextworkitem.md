---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d881f1be4e809cf45f100b966d6013ae8fa88f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="a3d88-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="a3d88-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a3d88-103">属性</span><span class="sxs-lookup"><span data-stu-id="a3d88-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3d88-104">ID</span><span class="sxs-lookup"><span data-stu-id="a3d88-104">ID</span></span>|<span data-ttu-id="a3d88-105">1026</span><span class="sxs-lookup"><span data-stu-id="a3d88-105">1026</span></span>|  
|<span data-ttu-id="a3d88-106">关键字</span><span class="sxs-lookup"><span data-stu-id="a3d88-106">Keywords</span></span>|<span data-ttu-id="a3d88-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a3d88-107">WFRuntime</span></span>|  
|<span data-ttu-id="a3d88-108">级别</span><span class="sxs-lookup"><span data-stu-id="a3d88-108">Level</span></span>|<span data-ttu-id="a3d88-109">详细</span><span class="sxs-lookup"><span data-stu-id="a3d88-109">Verbose</span></span>|  
|<span data-ttu-id="a3d88-110">通道</span><span class="sxs-lookup"><span data-stu-id="a3d88-110">Channel</span></span>|<span data-ttu-id="a3d88-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="a3d88-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a3d88-112">描述</span><span class="sxs-lookup"><span data-stu-id="a3d88-112">Description</span></span>  
 <span data-ttu-id="a3d88-113">指示已安排 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="a3d88-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a3d88-114">消息</span><span class="sxs-lookup"><span data-stu-id="a3d88-114">Message</span></span>  
 <span data-ttu-id="a3d88-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="a3d88-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a3d88-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="a3d88-116">Details</span></span>  
  
|<span data-ttu-id="a3d88-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="a3d88-117">Data Item Name</span></span>|<span data-ttu-id="a3d88-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="a3d88-118">Data Item Type</span></span>|<span data-ttu-id="a3d88-119">描述</span><span class="sxs-lookup"><span data-stu-id="a3d88-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a3d88-120">Activity</span><span class="sxs-lookup"><span data-stu-id="a3d88-120">Activity</span></span>|<span data-ttu-id="a3d88-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a3d88-121">xs:string</span></span>|<span data-ttu-id="a3d88-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="a3d88-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a3d88-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a3d88-123">DisplayName</span></span>|<span data-ttu-id="a3d88-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a3d88-124">xs:string</span></span>|<span data-ttu-id="a3d88-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a3d88-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a3d88-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a3d88-126">InstanceId</span></span>|<span data-ttu-id="a3d88-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a3d88-127">xs:string</span></span>|<span data-ttu-id="a3d88-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="a3d88-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a3d88-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a3d88-129">AppDomain</span></span>|<span data-ttu-id="a3d88-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a3d88-130">xs:string</span></span>|<span data-ttu-id="a3d88-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a3d88-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
