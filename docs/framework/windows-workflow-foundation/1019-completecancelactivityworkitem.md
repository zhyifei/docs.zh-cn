---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510203"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="0d7bf-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="0d7bf-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0d7bf-103">属性</span><span class="sxs-lookup"><span data-stu-id="0d7bf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d7bf-104">ID</span><span class="sxs-lookup"><span data-stu-id="0d7bf-104">ID</span></span>|<span data-ttu-id="0d7bf-105">1019</span><span class="sxs-lookup"><span data-stu-id="0d7bf-105">1019</span></span>|  
|<span data-ttu-id="0d7bf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0d7bf-106">Keywords</span></span>|<span data-ttu-id="0d7bf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0d7bf-107">WFRuntime</span></span>|  
|<span data-ttu-id="0d7bf-108">级别</span><span class="sxs-lookup"><span data-stu-id="0d7bf-108">Level</span></span>|<span data-ttu-id="0d7bf-109">详细</span><span class="sxs-lookup"><span data-stu-id="0d7bf-109">Verbose</span></span>|  
|<span data-ttu-id="0d7bf-110">通道</span><span class="sxs-lookup"><span data-stu-id="0d7bf-110">Channel</span></span>|<span data-ttu-id="0d7bf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="0d7bf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d7bf-112">描述</span><span class="sxs-lookup"><span data-stu-id="0d7bf-112">Description</span></span>  
 <span data-ttu-id="0d7bf-113">指示 CancelActivityWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d7bf-114">消息</span><span class="sxs-lookup"><span data-stu-id="0d7bf-114">Message</span></span>  
 <span data-ttu-id="0d7bf-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 CancelActivityWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d7bf-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="0d7bf-116">Details</span></span>  
  
|<span data-ttu-id="0d7bf-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0d7bf-117">Data Item Name</span></span>|<span data-ttu-id="0d7bf-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0d7bf-118">Data Item Type</span></span>|<span data-ttu-id="0d7bf-119">描述</span><span class="sxs-lookup"><span data-stu-id="0d7bf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d7bf-120">Activity</span><span class="sxs-lookup"><span data-stu-id="0d7bf-120">Activity</span></span>|<span data-ttu-id="0d7bf-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d7bf-121">xs:string</span></span>|<span data-ttu-id="0d7bf-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0d7bf-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0d7bf-123">DisplayName</span></span>|<span data-ttu-id="0d7bf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d7bf-124">xs:string</span></span>|<span data-ttu-id="0d7bf-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0d7bf-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0d7bf-126">InstanceId</span></span>|<span data-ttu-id="0d7bf-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d7bf-127">xs:string</span></span>|<span data-ttu-id="0d7bf-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0d7bf-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0d7bf-129">AppDomain</span></span>|<span data-ttu-id="0d7bf-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d7bf-130">xs:string</span></span>|<span data-ttu-id="0d7bf-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
