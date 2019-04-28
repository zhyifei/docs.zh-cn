---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008793"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="b7078-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="b7078-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b7078-103">属性</span><span class="sxs-lookup"><span data-stu-id="b7078-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7078-104">Id</span><span class="sxs-lookup"><span data-stu-id="b7078-104">ID</span></span>|<span data-ttu-id="b7078-105">1031</span><span class="sxs-lookup"><span data-stu-id="b7078-105">1031</span></span>|  
|<span data-ttu-id="b7078-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b7078-106">Keywords</span></span>|<span data-ttu-id="b7078-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b7078-107">WFRuntime</span></span>|  
|<span data-ttu-id="b7078-108">级别</span><span class="sxs-lookup"><span data-stu-id="b7078-108">Level</span></span>|<span data-ttu-id="b7078-109">详细</span><span class="sxs-lookup"><span data-stu-id="b7078-109">Verbose</span></span>|  
|<span data-ttu-id="b7078-110">通道</span><span class="sxs-lookup"><span data-stu-id="b7078-110">Channel</span></span>|<span data-ttu-id="b7078-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b7078-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b7078-112">描述</span><span class="sxs-lookup"><span data-stu-id="b7078-112">Description</span></span>  
 <span data-ttu-id="b7078-113">指示 FaultWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="b7078-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b7078-114">消息</span><span class="sxs-lookup"><span data-stu-id="b7078-114">Message</span></span>  
 <span data-ttu-id="b7078-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 FaultWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="b7078-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="b7078-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="b7078-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b7078-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="b7078-117">Details</span></span>  
  
|<span data-ttu-id="b7078-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b7078-118">Data Item Name</span></span>|<span data-ttu-id="b7078-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b7078-119">Data Item Type</span></span>|<span data-ttu-id="b7078-120">描述</span><span class="sxs-lookup"><span data-stu-id="b7078-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b7078-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="b7078-121">FaultActivity</span></span>|<span data-ttu-id="b7078-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-122">xs:string</span></span>|<span data-ttu-id="b7078-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="b7078-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="b7078-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b7078-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="b7078-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-125">xs:string</span></span>|<span data-ttu-id="b7078-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b7078-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="b7078-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b7078-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="b7078-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-128">xs:string</span></span>|<span data-ttu-id="b7078-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b7078-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="b7078-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="b7078-130">ExceptionActivity</span></span>|<span data-ttu-id="b7078-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-131">xs:string</span></span>|<span data-ttu-id="b7078-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="b7078-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b7078-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b7078-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="b7078-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-134">xs:string</span></span>|<span data-ttu-id="b7078-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b7078-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b7078-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b7078-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="b7078-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-137">xs:string</span></span>|<span data-ttu-id="b7078-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b7078-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b7078-139">例外</span><span class="sxs-lookup"><span data-stu-id="b7078-139">Exception</span></span>|<span data-ttu-id="b7078-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-140">xs:string</span></span>|<span data-ttu-id="b7078-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="b7078-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="b7078-142">应用程序域</span><span class="sxs-lookup"><span data-stu-id="b7078-142">AppDomain</span></span>|<span data-ttu-id="b7078-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7078-143">xs:string</span></span>|<span data-ttu-id="b7078-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b7078-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
