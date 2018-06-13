---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509692"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="c016e-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="c016e-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="c016e-103">属性</span><span class="sxs-lookup"><span data-stu-id="c016e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c016e-104">ID</span><span class="sxs-lookup"><span data-stu-id="c016e-104">ID</span></span>|<span data-ttu-id="c016e-105">1010</span><span class="sxs-lookup"><span data-stu-id="c016e-105">1010</span></span>|  
|<span data-ttu-id="c016e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c016e-106">Keywords</span></span>|<span data-ttu-id="c016e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c016e-107">WFRuntime</span></span>|  
|<span data-ttu-id="c016e-108">级别</span><span class="sxs-lookup"><span data-stu-id="c016e-108">Level</span></span>|<span data-ttu-id="c016e-109">信息</span><span class="sxs-lookup"><span data-stu-id="c016e-109">Information</span></span>|  
|<span data-ttu-id="c016e-110">通道</span><span class="sxs-lookup"><span data-stu-id="c016e-110">Channel</span></span>|<span data-ttu-id="c016e-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c016e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c016e-112">描述</span><span class="sxs-lookup"><span data-stu-id="c016e-112">Description</span></span>  
 <span data-ttu-id="c016e-113">指示活动已完成执行。</span><span class="sxs-lookup"><span data-stu-id="c016e-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c016e-114">消息</span><span class="sxs-lookup"><span data-stu-id="c016e-114">Message</span></span>  
 <span data-ttu-id="c016e-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”在“%4”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="c016e-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c016e-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c016e-116">Details</span></span>  
  
|<span data-ttu-id="c016e-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c016e-117">Data Item Name</span></span>|<span data-ttu-id="c016e-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c016e-118">Data Item Type</span></span>|<span data-ttu-id="c016e-119">描述</span><span class="sxs-lookup"><span data-stu-id="c016e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c016e-120">Activity</span><span class="sxs-lookup"><span data-stu-id="c016e-120">Activity</span></span>|<span data-ttu-id="c016e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c016e-121">xs:string</span></span>|<span data-ttu-id="c016e-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c016e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c016e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c016e-123">DisplayName</span></span>|<span data-ttu-id="c016e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c016e-124">xs:string</span></span>|<span data-ttu-id="c016e-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c016e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c016e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c016e-126">InstanceId</span></span>|<span data-ttu-id="c016e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c016e-127">xs:string</span></span>|<span data-ttu-id="c016e-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c016e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c016e-129">状态</span><span class="sxs-lookup"><span data-stu-id="c016e-129">State</span></span>|<span data-ttu-id="c016e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c016e-130">xs:string</span></span>|<span data-ttu-id="c016e-131">活动的状态。</span><span class="sxs-lookup"><span data-stu-id="c016e-131">The state of the activity.</span></span>|  
|<span data-ttu-id="c016e-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c016e-132">AppDomain</span></span>|<span data-ttu-id="c016e-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="c016e-133">xs:string</span></span>|<span data-ttu-id="c016e-134">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c016e-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
