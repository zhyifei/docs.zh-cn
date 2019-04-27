---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924743"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="f04f7-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="f04f7-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="f04f7-103">属性</span><span class="sxs-lookup"><span data-stu-id="f04f7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f04f7-104">Id</span><span class="sxs-lookup"><span data-stu-id="f04f7-104">ID</span></span>|<span data-ttu-id="f04f7-105">1020</span><span class="sxs-lookup"><span data-stu-id="f04f7-105">1020</span></span>|  
|<span data-ttu-id="f04f7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f04f7-106">Keywords</span></span>|<span data-ttu-id="f04f7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f04f7-107">WFRuntime</span></span>|  
|<span data-ttu-id="f04f7-108">级别</span><span class="sxs-lookup"><span data-stu-id="f04f7-108">Level</span></span>|<span data-ttu-id="f04f7-109">详细</span><span class="sxs-lookup"><span data-stu-id="f04f7-109">Verbose</span></span>|  
|<span data-ttu-id="f04f7-110">通道</span><span class="sxs-lookup"><span data-stu-id="f04f7-110">Channel</span></span>|<span data-ttu-id="f04f7-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="f04f7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f04f7-112">描述</span><span class="sxs-lookup"><span data-stu-id="f04f7-112">Description</span></span>  
 <span data-ttu-id="f04f7-113">指示已为活动创建了书签。</span><span class="sxs-lookup"><span data-stu-id="f04f7-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f04f7-114">消息</span><span class="sxs-lookup"><span data-stu-id="f04f7-114">Message</span></span>  
 <span data-ttu-id="f04f7-115">已为 Activity"%1"、 DisplayName 创建书签:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="f04f7-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f04f7-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="f04f7-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f04f7-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="f04f7-117">Details</span></span>  
  
|<span data-ttu-id="f04f7-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f04f7-118">Data Item Name</span></span>|<span data-ttu-id="f04f7-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f04f7-119">Data Item Type</span></span>|<span data-ttu-id="f04f7-120">描述</span><span class="sxs-lookup"><span data-stu-id="f04f7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f04f7-121">活动</span><span class="sxs-lookup"><span data-stu-id="f04f7-121">Activity</span></span>|<span data-ttu-id="f04f7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f04f7-122">xs:string</span></span>|<span data-ttu-id="f04f7-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f04f7-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="f04f7-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f04f7-124">DisplayName</span></span>|<span data-ttu-id="f04f7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f04f7-125">xs:string</span></span>|<span data-ttu-id="f04f7-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f04f7-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="f04f7-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f04f7-127">InstanceId</span></span>|<span data-ttu-id="f04f7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f04f7-128">xs:string</span></span>|<span data-ttu-id="f04f7-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="f04f7-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f04f7-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="f04f7-130">BookmarkName</span></span>|<span data-ttu-id="f04f7-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f04f7-131">xs:string</span></span>|<span data-ttu-id="f04f7-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="f04f7-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="f04f7-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="f04f7-133">BookmarkScope</span></span>|<span data-ttu-id="f04f7-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f04f7-134">xs:string</span></span>|<span data-ttu-id="f04f7-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="f04f7-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="f04f7-136">应用程序域</span><span class="sxs-lookup"><span data-stu-id="f04f7-136">AppDomain</span></span>|<span data-ttu-id="f04f7-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f04f7-137">xs:string</span></span>|<span data-ttu-id="f04f7-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f04f7-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
