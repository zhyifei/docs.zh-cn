---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510454"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="1ef54-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="1ef54-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="1ef54-103">属性</span><span class="sxs-lookup"><span data-stu-id="1ef54-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ef54-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ef54-104">ID</span></span>|<span data-ttu-id="1ef54-105">1020</span><span class="sxs-lookup"><span data-stu-id="1ef54-105">1020</span></span>|  
|<span data-ttu-id="1ef54-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1ef54-106">Keywords</span></span>|<span data-ttu-id="1ef54-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1ef54-107">WFRuntime</span></span>|  
|<span data-ttu-id="1ef54-108">级别</span><span class="sxs-lookup"><span data-stu-id="1ef54-108">Level</span></span>|<span data-ttu-id="1ef54-109">详细</span><span class="sxs-lookup"><span data-stu-id="1ef54-109">Verbose</span></span>|  
|<span data-ttu-id="1ef54-110">通道</span><span class="sxs-lookup"><span data-stu-id="1ef54-110">Channel</span></span>|<span data-ttu-id="1ef54-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1ef54-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ef54-112">描述</span><span class="sxs-lookup"><span data-stu-id="1ef54-112">Description</span></span>  
 <span data-ttu-id="1ef54-113">指示已为活动创建了书签。</span><span class="sxs-lookup"><span data-stu-id="1ef54-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ef54-114">消息</span><span class="sxs-lookup"><span data-stu-id="1ef54-114">Message</span></span>  
 <span data-ttu-id="1ef54-115">已为 Activity"%1"、 DisplayName 创建书签:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="1ef54-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="1ef54-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="1ef54-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ef54-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ef54-117">Details</span></span>  
  
|<span data-ttu-id="1ef54-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1ef54-118">Data Item Name</span></span>|<span data-ttu-id="1ef54-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1ef54-119">Data Item Type</span></span>|<span data-ttu-id="1ef54-120">描述</span><span class="sxs-lookup"><span data-stu-id="1ef54-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ef54-121">Activity</span><span class="sxs-lookup"><span data-stu-id="1ef54-121">Activity</span></span>|<span data-ttu-id="1ef54-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ef54-122">xs:string</span></span>|<span data-ttu-id="1ef54-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1ef54-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="1ef54-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1ef54-124">DisplayName</span></span>|<span data-ttu-id="1ef54-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ef54-125">xs:string</span></span>|<span data-ttu-id="1ef54-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1ef54-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="1ef54-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1ef54-127">InstanceId</span></span>|<span data-ttu-id="1ef54-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ef54-128">xs:string</span></span>|<span data-ttu-id="1ef54-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1ef54-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1ef54-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="1ef54-130">BookmarkName</span></span>|<span data-ttu-id="1ef54-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ef54-131">xs:string</span></span>|<span data-ttu-id="1ef54-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="1ef54-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="1ef54-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="1ef54-133">BookmarkScope</span></span>|<span data-ttu-id="1ef54-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ef54-134">xs:string</span></span>|<span data-ttu-id="1ef54-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="1ef54-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="1ef54-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ef54-136">AppDomain</span></span>|<span data-ttu-id="1ef54-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ef54-137">xs:string</span></span>|<span data-ttu-id="1ef54-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1ef54-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
