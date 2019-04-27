---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008366"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="22363-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="22363-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="22363-103">属性</span><span class="sxs-lookup"><span data-stu-id="22363-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22363-104">Id</span><span class="sxs-lookup"><span data-stu-id="22363-104">ID</span></span>|<span data-ttu-id="22363-105">1010</span><span class="sxs-lookup"><span data-stu-id="22363-105">1010</span></span>|  
|<span data-ttu-id="22363-106">关键字</span><span class="sxs-lookup"><span data-stu-id="22363-106">Keywords</span></span>|<span data-ttu-id="22363-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="22363-107">WFRuntime</span></span>|  
|<span data-ttu-id="22363-108">级别</span><span class="sxs-lookup"><span data-stu-id="22363-108">Level</span></span>|<span data-ttu-id="22363-109">信息</span><span class="sxs-lookup"><span data-stu-id="22363-109">Information</span></span>|  
|<span data-ttu-id="22363-110">通道</span><span class="sxs-lookup"><span data-stu-id="22363-110">Channel</span></span>|<span data-ttu-id="22363-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="22363-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="22363-112">描述</span><span class="sxs-lookup"><span data-stu-id="22363-112">Description</span></span>  
 <span data-ttu-id="22363-113">指示活动已完成执行。</span><span class="sxs-lookup"><span data-stu-id="22363-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="22363-114">消息</span><span class="sxs-lookup"><span data-stu-id="22363-114">Message</span></span>  
 <span data-ttu-id="22363-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”在“%4”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="22363-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="22363-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="22363-116">Details</span></span>  
  
|<span data-ttu-id="22363-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="22363-117">Data Item Name</span></span>|<span data-ttu-id="22363-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="22363-118">Data Item Type</span></span>|<span data-ttu-id="22363-119">描述</span><span class="sxs-lookup"><span data-stu-id="22363-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="22363-120">活动</span><span class="sxs-lookup"><span data-stu-id="22363-120">Activity</span></span>|<span data-ttu-id="22363-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="22363-121">xs:string</span></span>|<span data-ttu-id="22363-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="22363-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="22363-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="22363-123">DisplayName</span></span>|<span data-ttu-id="22363-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="22363-124">xs:string</span></span>|<span data-ttu-id="22363-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="22363-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="22363-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="22363-126">InstanceId</span></span>|<span data-ttu-id="22363-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="22363-127">xs:string</span></span>|<span data-ttu-id="22363-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="22363-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="22363-129">状态</span><span class="sxs-lookup"><span data-stu-id="22363-129">State</span></span>|<span data-ttu-id="22363-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="22363-130">xs:string</span></span>|<span data-ttu-id="22363-131">活动的状态。</span><span class="sxs-lookup"><span data-stu-id="22363-131">The state of the activity.</span></span>|  
|<span data-ttu-id="22363-132">应用程序域</span><span class="sxs-lookup"><span data-stu-id="22363-132">AppDomain</span></span>|<span data-ttu-id="22363-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="22363-133">xs:string</span></span>|<span data-ttu-id="22363-134">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="22363-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
