---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924418"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="f3cf2-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="f3cf2-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f3cf2-103">属性</span><span class="sxs-lookup"><span data-stu-id="f3cf2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3cf2-104">Id</span><span class="sxs-lookup"><span data-stu-id="f3cf2-104">ID</span></span>|<span data-ttu-id="f3cf2-105">1021</span><span class="sxs-lookup"><span data-stu-id="f3cf2-105">1021</span></span>|  
|<span data-ttu-id="f3cf2-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f3cf2-106">Keywords</span></span>|<span data-ttu-id="f3cf2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f3cf2-107">WFRuntime</span></span>|  
|<span data-ttu-id="f3cf2-108">级别</span><span class="sxs-lookup"><span data-stu-id="f3cf2-108">Level</span></span>|<span data-ttu-id="f3cf2-109">详细</span><span class="sxs-lookup"><span data-stu-id="f3cf2-109">Verbose</span></span>|  
|<span data-ttu-id="f3cf2-110">通道</span><span class="sxs-lookup"><span data-stu-id="f3cf2-110">Channel</span></span>|<span data-ttu-id="f3cf2-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="f3cf2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f3cf2-112">描述</span><span class="sxs-lookup"><span data-stu-id="f3cf2-112">Description</span></span>  
 <span data-ttu-id="f3cf2-113">指示已安排 BookmarkWorkItem。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f3cf2-114">消息</span><span class="sxs-lookup"><span data-stu-id="f3cf2-114">Message</span></span>  
 <span data-ttu-id="f3cf2-115">已为 Activity"%1"、 DisplayName 安排了 BookmarkWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f3cf2-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f3cf2-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="f3cf2-117">Details</span></span>  
  
|<span data-ttu-id="f3cf2-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f3cf2-118">Data Item Name</span></span>|<span data-ttu-id="f3cf2-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f3cf2-119">Data Item Type</span></span>|<span data-ttu-id="f3cf2-120">描述</span><span class="sxs-lookup"><span data-stu-id="f3cf2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f3cf2-121">活动</span><span class="sxs-lookup"><span data-stu-id="f3cf2-121">Activity</span></span>|<span data-ttu-id="f3cf2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3cf2-122">xs:string</span></span>|<span data-ttu-id="f3cf2-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="f3cf2-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f3cf2-124">DisplayName</span></span>|<span data-ttu-id="f3cf2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3cf2-125">xs:string</span></span>|<span data-ttu-id="f3cf2-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="f3cf2-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f3cf2-127">InstanceId</span></span>|<span data-ttu-id="f3cf2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3cf2-128">xs:string</span></span>|<span data-ttu-id="f3cf2-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f3cf2-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="f3cf2-130">BookmarkName</span></span>|<span data-ttu-id="f3cf2-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3cf2-131">xs:string</span></span>|<span data-ttu-id="f3cf2-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="f3cf2-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="f3cf2-133">BookmarkScope</span></span>|<span data-ttu-id="f3cf2-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3cf2-134">xs:string</span></span>|<span data-ttu-id="f3cf2-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="f3cf2-136">应用程序域</span><span class="sxs-lookup"><span data-stu-id="f3cf2-136">AppDomain</span></span>|<span data-ttu-id="f3cf2-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3cf2-137">xs:string</span></span>|<span data-ttu-id="f3cf2-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f3cf2-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
