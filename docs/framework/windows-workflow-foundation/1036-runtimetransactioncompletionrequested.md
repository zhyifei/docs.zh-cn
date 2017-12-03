---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 112063d5cd550f438541b2d775eaa49124d9cc02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="c1238-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="c1238-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="c1238-103">属性</span><span class="sxs-lookup"><span data-stu-id="c1238-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1238-104">ID</span><span class="sxs-lookup"><span data-stu-id="c1238-104">ID</span></span>|<span data-ttu-id="c1238-105">1036</span><span class="sxs-lookup"><span data-stu-id="c1238-105">1036</span></span>|  
|<span data-ttu-id="c1238-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c1238-106">Keywords</span></span>|<span data-ttu-id="c1238-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c1238-107">WFRuntime</span></span>|  
|<span data-ttu-id="c1238-108">级别</span><span class="sxs-lookup"><span data-stu-id="c1238-108">Level</span></span>|<span data-ttu-id="c1238-109">详细</span><span class="sxs-lookup"><span data-stu-id="c1238-109">Verbose</span></span>|  
|<span data-ttu-id="c1238-110">通道</span><span class="sxs-lookup"><span data-stu-id="c1238-110">Channel</span></span>|<span data-ttu-id="c1238-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c1238-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c1238-112">描述</span><span class="sxs-lookup"><span data-stu-id="c1238-112">Description</span></span>  
 <span data-ttu-id="c1238-113">指示活动已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="c1238-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c1238-114">消息</span><span class="sxs-lookup"><span data-stu-id="c1238-114">Message</span></span>  
 <span data-ttu-id="c1238-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="c1238-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c1238-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c1238-116">Details</span></span>  
  
|<span data-ttu-id="c1238-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c1238-117">Data Item Name</span></span>|<span data-ttu-id="c1238-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c1238-118">Data Item Type</span></span>|<span data-ttu-id="c1238-119">描述</span><span class="sxs-lookup"><span data-stu-id="c1238-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c1238-120">Activity</span><span class="sxs-lookup"><span data-stu-id="c1238-120">Activity</span></span>|<span data-ttu-id="c1238-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1238-121">xs:string</span></span>|<span data-ttu-id="c1238-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c1238-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c1238-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c1238-123">DisplayName</span></span>|<span data-ttu-id="c1238-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1238-124">xs:string</span></span>|<span data-ttu-id="c1238-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c1238-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c1238-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c1238-126">InstanceId</span></span>|<span data-ttu-id="c1238-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1238-127">xs:string</span></span>|<span data-ttu-id="c1238-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c1238-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c1238-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c1238-129">AppDomain</span></span>|<span data-ttu-id="c1238-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1238-130">xs:string</span></span>|<span data-ttu-id="c1238-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c1238-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
