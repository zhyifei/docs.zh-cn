---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510029"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="f4d5b-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="f4d5b-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="f4d5b-103">属性</span><span class="sxs-lookup"><span data-stu-id="f4d5b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4d5b-104">ID</span><span class="sxs-lookup"><span data-stu-id="f4d5b-104">ID</span></span>|<span data-ttu-id="f4d5b-105">1035</span><span class="sxs-lookup"><span data-stu-id="f4d5b-105">1035</span></span>|  
|<span data-ttu-id="f4d5b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f4d5b-106">Keywords</span></span>|<span data-ttu-id="f4d5b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f4d5b-107">WFRuntime</span></span>|  
|<span data-ttu-id="f4d5b-108">级别</span><span class="sxs-lookup"><span data-stu-id="f4d5b-108">Level</span></span>|<span data-ttu-id="f4d5b-109">详细</span><span class="sxs-lookup"><span data-stu-id="f4d5b-109">Verbose</span></span>|  
|<span data-ttu-id="f4d5b-110">通道</span><span class="sxs-lookup"><span data-stu-id="f4d5b-110">Channel</span></span>|<span data-ttu-id="f4d5b-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="f4d5b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f4d5b-112">描述</span><span class="sxs-lookup"><span data-stu-id="f4d5b-112">Description</span></span>  
 <span data-ttu-id="f4d5b-113">指示活动已设置为运行时事务。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f4d5b-114">消息</span><span class="sxs-lookup"><span data-stu-id="f4d5b-114">Message</span></span>  
 <span data-ttu-id="f4d5b-115">运行时事务已设置 Activity"%1"、 DisplayName:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f4d5b-116">执行隔离到活动"%4"、 DisplayName:"%5"、 InstanceId:"%6"。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4d5b-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="f4d5b-117">Details</span></span>  
  
|<span data-ttu-id="f4d5b-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f4d5b-118">Data Item Name</span></span>|<span data-ttu-id="f4d5b-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f4d5b-119">Data Item Type</span></span>|<span data-ttu-id="f4d5b-120">描述</span><span class="sxs-lookup"><span data-stu-id="f4d5b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f4d5b-121">Activity</span><span class="sxs-lookup"><span data-stu-id="f4d5b-121">Activity</span></span>|<span data-ttu-id="f4d5b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4d5b-122">xs:string</span></span>|<span data-ttu-id="f4d5b-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="f4d5b-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f4d5b-124">DisplayName</span></span>|<span data-ttu-id="f4d5b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4d5b-125">xs:string</span></span>|<span data-ttu-id="f4d5b-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="f4d5b-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f4d5b-127">InstanceId</span></span>|<span data-ttu-id="f4d5b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4d5b-128">xs:string</span></span>|<span data-ttu-id="f4d5b-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f4d5b-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="f4d5b-130">IsolatedActivity</span></span>|<span data-ttu-id="f4d5b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4d5b-131">xs:string</span></span>|<span data-ttu-id="f4d5b-132">事务隔离到的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="f4d5b-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f4d5b-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="f4d5b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4d5b-134">xs:string</span></span>|<span data-ttu-id="f4d5b-135">事务隔离到的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="f4d5b-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f4d5b-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="f4d5b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4d5b-137">xs:string</span></span>|<span data-ttu-id="f4d5b-138">事务隔离到的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="f4d5b-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f4d5b-139">AppDomain</span></span>|<span data-ttu-id="f4d5b-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4d5b-140">xs:string</span></span>|<span data-ttu-id="f4d5b-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f4d5b-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
