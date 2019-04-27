---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924353"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="a6e86-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="a6e86-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a6e86-103">属性</span><span class="sxs-lookup"><span data-stu-id="a6e86-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6e86-104">Id</span><span class="sxs-lookup"><span data-stu-id="a6e86-104">ID</span></span>|<span data-ttu-id="a6e86-105">1029</span><span class="sxs-lookup"><span data-stu-id="a6e86-105">1029</span></span>|  
|<span data-ttu-id="a6e86-106">关键字</span><span class="sxs-lookup"><span data-stu-id="a6e86-106">Keywords</span></span>|<span data-ttu-id="a6e86-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a6e86-107">WFRuntime</span></span>|  
|<span data-ttu-id="a6e86-108">级别</span><span class="sxs-lookup"><span data-stu-id="a6e86-108">Level</span></span>|<span data-ttu-id="a6e86-109">详细</span><span class="sxs-lookup"><span data-stu-id="a6e86-109">Verbose</span></span>|  
|<span data-ttu-id="a6e86-110">通道</span><span class="sxs-lookup"><span data-stu-id="a6e86-110">Channel</span></span>|<span data-ttu-id="a6e86-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="a6e86-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6e86-112">描述</span><span class="sxs-lookup"><span data-stu-id="a6e86-112">Description</span></span>  
 <span data-ttu-id="a6e86-113">指示已安排 FaultWorkItem。</span><span class="sxs-lookup"><span data-stu-id="a6e86-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6e86-114">消息</span><span class="sxs-lookup"><span data-stu-id="a6e86-114">Message</span></span>  
 <span data-ttu-id="a6e86-115">已为 Activity"%1"、 DisplayName 安排了 FaultWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="a6e86-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="a6e86-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="a6e86-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6e86-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="a6e86-117">Details</span></span>  
  
|<span data-ttu-id="a6e86-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="a6e86-118">Data Item Name</span></span>|<span data-ttu-id="a6e86-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="a6e86-119">Data Item Type</span></span>|<span data-ttu-id="a6e86-120">描述</span><span class="sxs-lookup"><span data-stu-id="a6e86-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6e86-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="a6e86-121">FaultActivity</span></span>|<span data-ttu-id="a6e86-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-122">xs:string</span></span>|<span data-ttu-id="a6e86-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="a6e86-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="a6e86-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a6e86-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="a6e86-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-125">xs:string</span></span>|<span data-ttu-id="a6e86-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a6e86-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="a6e86-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a6e86-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="a6e86-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-128">xs:string</span></span>|<span data-ttu-id="a6e86-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="a6e86-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="a6e86-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="a6e86-130">ExceptionActivity</span></span>|<span data-ttu-id="a6e86-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-131">xs:string</span></span>|<span data-ttu-id="a6e86-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="a6e86-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a6e86-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a6e86-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="a6e86-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-134">xs:string</span></span>|<span data-ttu-id="a6e86-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a6e86-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a6e86-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a6e86-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="a6e86-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-137">xs:string</span></span>|<span data-ttu-id="a6e86-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="a6e86-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a6e86-139">例外</span><span class="sxs-lookup"><span data-stu-id="a6e86-139">Exception</span></span>|<span data-ttu-id="a6e86-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-140">xs:string</span></span>|<span data-ttu-id="a6e86-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="a6e86-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="a6e86-142">应用程序域</span><span class="sxs-lookup"><span data-stu-id="a6e86-142">AppDomain</span></span>|<span data-ttu-id="a6e86-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e86-143">xs:string</span></span>|<span data-ttu-id="a6e86-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6e86-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
