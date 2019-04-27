---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: c1ff62bb4143bb798ea7adb7c3fee539ef68bc37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925185"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="67681-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="67681-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="67681-103">属性</span><span class="sxs-lookup"><span data-stu-id="67681-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67681-104">Id</span><span class="sxs-lookup"><span data-stu-id="67681-104">ID</span></span>|<span data-ttu-id="67681-105">1013</span><span class="sxs-lookup"><span data-stu-id="67681-105">1013</span></span>|  
|<span data-ttu-id="67681-106">关键字</span><span class="sxs-lookup"><span data-stu-id="67681-106">Keywords</span></span>|<span data-ttu-id="67681-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="67681-107">WFRuntime</span></span>|  
|<span data-ttu-id="67681-108">级别</span><span class="sxs-lookup"><span data-stu-id="67681-108">Level</span></span>|<span data-ttu-id="67681-109">详细</span><span class="sxs-lookup"><span data-stu-id="67681-109">Verbose</span></span>|  
|<span data-ttu-id="67681-110">通道</span><span class="sxs-lookup"><span data-stu-id="67681-110">Channel</span></span>|<span data-ttu-id="67681-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="67681-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="67681-112">描述</span><span class="sxs-lookup"><span data-stu-id="67681-112">Description</span></span>  
 <span data-ttu-id="67681-113">指示 ExecuteActivityWorkItem 已完成</span><span class="sxs-lookup"><span data-stu-id="67681-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="67681-114">消息</span><span class="sxs-lookup"><span data-stu-id="67681-114">Message</span></span>  
 <span data-ttu-id="67681-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 ExecuteActivityWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="67681-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="67681-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="67681-116">Details</span></span>  
  
|<span data-ttu-id="67681-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="67681-117">Data Item Name</span></span>|<span data-ttu-id="67681-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="67681-118">Data Item Type</span></span>|<span data-ttu-id="67681-119">描述</span><span class="sxs-lookup"><span data-stu-id="67681-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="67681-120">活动</span><span class="sxs-lookup"><span data-stu-id="67681-120">Activity</span></span>|<span data-ttu-id="67681-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="67681-121">xs:string</span></span>|<span data-ttu-id="67681-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="67681-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="67681-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="67681-123">DisplayName</span></span>|<span data-ttu-id="67681-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="67681-124">xs:string</span></span>|<span data-ttu-id="67681-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="67681-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="67681-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="67681-126">InstanceId</span></span>|<span data-ttu-id="67681-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="67681-127">xs:string</span></span>|<span data-ttu-id="67681-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="67681-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="67681-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="67681-129">AppDomain</span></span>|<span data-ttu-id="67681-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="67681-130">xs:string</span></span>|<span data-ttu-id="67681-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="67681-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
