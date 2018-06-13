---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: bd49c608a8f6a6caab6975850507a00a2c0edb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509653"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="bc1d9-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="bc1d9-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bc1d9-103">属性</span><span class="sxs-lookup"><span data-stu-id="bc1d9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc1d9-104">ID</span><span class="sxs-lookup"><span data-stu-id="bc1d9-104">ID</span></span>|<span data-ttu-id="bc1d9-105">1034</span><span class="sxs-lookup"><span data-stu-id="bc1d9-105">1034</span></span>|  
|<span data-ttu-id="bc1d9-106">关键字</span><span class="sxs-lookup"><span data-stu-id="bc1d9-106">Keywords</span></span>|<span data-ttu-id="bc1d9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bc1d9-107">WFRuntime</span></span>|  
|<span data-ttu-id="bc1d9-108">级别</span><span class="sxs-lookup"><span data-stu-id="bc1d9-108">Level</span></span>|<span data-ttu-id="bc1d9-109">详细</span><span class="sxs-lookup"><span data-stu-id="bc1d9-109">Verbose</span></span>|  
|<span data-ttu-id="bc1d9-110">通道</span><span class="sxs-lookup"><span data-stu-id="bc1d9-110">Channel</span></span>|<span data-ttu-id="bc1d9-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="bc1d9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bc1d9-112">描述</span><span class="sxs-lookup"><span data-stu-id="bc1d9-112">Description</span></span>  
 <span data-ttu-id="bc1d9-113">指示 RuntimeWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="bc1d9-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bc1d9-114">消息</span><span class="sxs-lookup"><span data-stu-id="bc1d9-114">Message</span></span>  
 <span data-ttu-id="bc1d9-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的运行时工作项已经完成。</span><span class="sxs-lookup"><span data-stu-id="bc1d9-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bc1d9-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="bc1d9-116">Details</span></span>  
  
|<span data-ttu-id="bc1d9-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="bc1d9-117">Data Item Name</span></span>|<span data-ttu-id="bc1d9-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="bc1d9-118">Data Item Type</span></span>|<span data-ttu-id="bc1d9-119">描述</span><span class="sxs-lookup"><span data-stu-id="bc1d9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bc1d9-120">Activity</span><span class="sxs-lookup"><span data-stu-id="bc1d9-120">Activity</span></span>|<span data-ttu-id="bc1d9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc1d9-121">xs:string</span></span>|<span data-ttu-id="bc1d9-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="bc1d9-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bc1d9-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bc1d9-123">DisplayName</span></span>|<span data-ttu-id="bc1d9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc1d9-124">xs:string</span></span>|<span data-ttu-id="bc1d9-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="bc1d9-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bc1d9-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bc1d9-126">InstanceId</span></span>|<span data-ttu-id="bc1d9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc1d9-127">xs:string</span></span>|<span data-ttu-id="bc1d9-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="bc1d9-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bc1d9-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bc1d9-129">AppDomain</span></span>|<span data-ttu-id="bc1d9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc1d9-130">xs:string</span></span>|<span data-ttu-id="bc1d9-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="bc1d9-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
