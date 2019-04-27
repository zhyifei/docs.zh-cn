---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 93d906b32b51effaa709da6763f535708cd6f821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924717"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="c4de4-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="c4de4-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c4de4-103">属性</span><span class="sxs-lookup"><span data-stu-id="c4de4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4de4-104">Id</span><span class="sxs-lookup"><span data-stu-id="c4de4-104">ID</span></span>|<span data-ttu-id="c4de4-105">1022</span><span class="sxs-lookup"><span data-stu-id="c4de4-105">1022</span></span>|  
|<span data-ttu-id="c4de4-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c4de4-106">Keywords</span></span>|<span data-ttu-id="c4de4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c4de4-107">WFRuntime</span></span>|  
|<span data-ttu-id="c4de4-108">级别</span><span class="sxs-lookup"><span data-stu-id="c4de4-108">Level</span></span>|<span data-ttu-id="c4de4-109">详细</span><span class="sxs-lookup"><span data-stu-id="c4de4-109">Verbose</span></span>|  
|<span data-ttu-id="c4de4-110">通道</span><span class="sxs-lookup"><span data-stu-id="c4de4-110">Channel</span></span>|<span data-ttu-id="c4de4-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c4de4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c4de4-112">描述</span><span class="sxs-lookup"><span data-stu-id="c4de4-112">Description</span></span>  
 <span data-ttu-id="c4de4-113">指示 BookmarkWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="c4de4-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c4de4-114">消息</span><span class="sxs-lookup"><span data-stu-id="c4de4-114">Message</span></span>  
 <span data-ttu-id="c4de4-115">开始为 Activity"%1"、 DisplayName BookmarkWorkItem 执行:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="c4de4-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c4de4-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="c4de4-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c4de4-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="c4de4-117">Details</span></span>  
  
|<span data-ttu-id="c4de4-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c4de4-118">Data Item Name</span></span>|<span data-ttu-id="c4de4-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c4de4-119">Data Item Type</span></span>|<span data-ttu-id="c4de4-120">描述</span><span class="sxs-lookup"><span data-stu-id="c4de4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c4de4-121">活动</span><span class="sxs-lookup"><span data-stu-id="c4de4-121">Activity</span></span>|<span data-ttu-id="c4de4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4de4-122">xs:string</span></span>|<span data-ttu-id="c4de4-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c4de4-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="c4de4-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c4de4-124">DisplayName</span></span>|<span data-ttu-id="c4de4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4de4-125">xs:string</span></span>|<span data-ttu-id="c4de4-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c4de4-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="c4de4-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c4de4-127">InstanceId</span></span>|<span data-ttu-id="c4de4-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4de4-128">xs:string</span></span>|<span data-ttu-id="c4de4-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c4de4-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c4de4-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="c4de4-130">BookmarkName</span></span>|<span data-ttu-id="c4de4-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4de4-131">xs:string</span></span>|<span data-ttu-id="c4de4-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="c4de4-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="c4de4-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="c4de4-133">BookmarkScope</span></span>|<span data-ttu-id="c4de4-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4de4-134">xs:string</span></span>|<span data-ttu-id="c4de4-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="c4de4-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="c4de4-136">应用程序域</span><span class="sxs-lookup"><span data-stu-id="c4de4-136">AppDomain</span></span>|<span data-ttu-id="c4de4-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4de4-137">xs:string</span></span>|<span data-ttu-id="c4de4-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c4de4-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
