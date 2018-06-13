---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509610"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="c3f30-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="c3f30-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c3f30-103">属性</span><span class="sxs-lookup"><span data-stu-id="c3f30-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3f30-104">ID</span><span class="sxs-lookup"><span data-stu-id="c3f30-104">ID</span></span>|<span data-ttu-id="c3f30-105">1011</span><span class="sxs-lookup"><span data-stu-id="c3f30-105">1011</span></span>|  
|<span data-ttu-id="c3f30-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c3f30-106">Keywords</span></span>|<span data-ttu-id="c3f30-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c3f30-107">WFRuntime</span></span>|  
|<span data-ttu-id="c3f30-108">级别</span><span class="sxs-lookup"><span data-stu-id="c3f30-108">Level</span></span>|<span data-ttu-id="c3f30-109">详细</span><span class="sxs-lookup"><span data-stu-id="c3f30-109">Verbose</span></span>|  
|<span data-ttu-id="c3f30-110">通道</span><span class="sxs-lookup"><span data-stu-id="c3f30-110">Channel</span></span>|<span data-ttu-id="c3f30-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c3f30-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3f30-112">描述</span><span class="sxs-lookup"><span data-stu-id="c3f30-112">Description</span></span>  
 <span data-ttu-id="c3f30-113">指示已安排 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="c3f30-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3f30-114">消息</span><span class="sxs-lookup"><span data-stu-id="c3f30-114">Message</span></span>  
 <span data-ttu-id="c3f30-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="c3f30-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3f30-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3f30-116">Details</span></span>  
  
|<span data-ttu-id="c3f30-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c3f30-117">Data Item Name</span></span>|<span data-ttu-id="c3f30-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c3f30-118">Data Item Type</span></span>|<span data-ttu-id="c3f30-119">描述</span><span class="sxs-lookup"><span data-stu-id="c3f30-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3f30-120">Activity</span><span class="sxs-lookup"><span data-stu-id="c3f30-120">Activity</span></span>|<span data-ttu-id="c3f30-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3f30-121">xs:string</span></span>|<span data-ttu-id="c3f30-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c3f30-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c3f30-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c3f30-123">DisplayName</span></span>|<span data-ttu-id="c3f30-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3f30-124">xs:string</span></span>|<span data-ttu-id="c3f30-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c3f30-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c3f30-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c3f30-126">InstanceId</span></span>|<span data-ttu-id="c3f30-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3f30-127">xs:string</span></span>|<span data-ttu-id="c3f30-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c3f30-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c3f30-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c3f30-129">AppDomain</span></span>|<span data-ttu-id="c3f30-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3f30-130">xs:string</span></span>|<span data-ttu-id="c3f30-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c3f30-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
