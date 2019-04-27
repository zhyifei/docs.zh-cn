---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924847"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="fbf53-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="fbf53-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="fbf53-103">属性</span><span class="sxs-lookup"><span data-stu-id="fbf53-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbf53-104">Id</span><span class="sxs-lookup"><span data-stu-id="fbf53-104">ID</span></span>|<span data-ttu-id="fbf53-105">1035</span><span class="sxs-lookup"><span data-stu-id="fbf53-105">1035</span></span>|  
|<span data-ttu-id="fbf53-106">关键字</span><span class="sxs-lookup"><span data-stu-id="fbf53-106">Keywords</span></span>|<span data-ttu-id="fbf53-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fbf53-107">WFRuntime</span></span>|  
|<span data-ttu-id="fbf53-108">级别</span><span class="sxs-lookup"><span data-stu-id="fbf53-108">Level</span></span>|<span data-ttu-id="fbf53-109">详细</span><span class="sxs-lookup"><span data-stu-id="fbf53-109">Verbose</span></span>|  
|<span data-ttu-id="fbf53-110">通道</span><span class="sxs-lookup"><span data-stu-id="fbf53-110">Channel</span></span>|<span data-ttu-id="fbf53-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="fbf53-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fbf53-112">描述</span><span class="sxs-lookup"><span data-stu-id="fbf53-112">Description</span></span>  
 <span data-ttu-id="fbf53-113">指示活动已设置为运行时事务。</span><span class="sxs-lookup"><span data-stu-id="fbf53-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fbf53-114">消息</span><span class="sxs-lookup"><span data-stu-id="fbf53-114">Message</span></span>  
 <span data-ttu-id="fbf53-115">运行时事务已由 Activity"%1"、 DisplayName 设置:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="fbf53-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="fbf53-116">执行独立于"%4"、 DisplayName:"%5"、 InstanceId:"%6"。</span><span class="sxs-lookup"><span data-stu-id="fbf53-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fbf53-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="fbf53-117">Details</span></span>  
  
|<span data-ttu-id="fbf53-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="fbf53-118">Data Item Name</span></span>|<span data-ttu-id="fbf53-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="fbf53-119">Data Item Type</span></span>|<span data-ttu-id="fbf53-120">描述</span><span class="sxs-lookup"><span data-stu-id="fbf53-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fbf53-121">活动</span><span class="sxs-lookup"><span data-stu-id="fbf53-121">Activity</span></span>|<span data-ttu-id="fbf53-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbf53-122">xs:string</span></span>|<span data-ttu-id="fbf53-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="fbf53-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="fbf53-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fbf53-124">DisplayName</span></span>|<span data-ttu-id="fbf53-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbf53-125">xs:string</span></span>|<span data-ttu-id="fbf53-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fbf53-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="fbf53-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fbf53-127">InstanceId</span></span>|<span data-ttu-id="fbf53-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbf53-128">xs:string</span></span>|<span data-ttu-id="fbf53-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="fbf53-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fbf53-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="fbf53-130">IsolatedActivity</span></span>|<span data-ttu-id="fbf53-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbf53-131">xs:string</span></span>|<span data-ttu-id="fbf53-132">事务隔离到的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="fbf53-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="fbf53-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fbf53-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="fbf53-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbf53-134">xs:string</span></span>|<span data-ttu-id="fbf53-135">事务隔离到的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fbf53-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="fbf53-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fbf53-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="fbf53-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbf53-137">xs:string</span></span>|<span data-ttu-id="fbf53-138">事务隔离到的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="fbf53-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="fbf53-139">应用程序域</span><span class="sxs-lookup"><span data-stu-id="fbf53-139">AppDomain</span></span>|<span data-ttu-id="fbf53-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbf53-140">xs:string</span></span>|<span data-ttu-id="fbf53-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="fbf53-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
