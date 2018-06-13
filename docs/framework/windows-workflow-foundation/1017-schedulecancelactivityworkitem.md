---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510167"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="1a2eb-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="1a2eb-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="1a2eb-103">属性</span><span class="sxs-lookup"><span data-stu-id="1a2eb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a2eb-104">ID</span><span class="sxs-lookup"><span data-stu-id="1a2eb-104">ID</span></span>|<span data-ttu-id="1a2eb-105">1017</span><span class="sxs-lookup"><span data-stu-id="1a2eb-105">1017</span></span>|  
|<span data-ttu-id="1a2eb-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1a2eb-106">Keywords</span></span>|<span data-ttu-id="1a2eb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1a2eb-107">WFRuntime</span></span>|  
|<span data-ttu-id="1a2eb-108">级别</span><span class="sxs-lookup"><span data-stu-id="1a2eb-108">Level</span></span>|<span data-ttu-id="1a2eb-109">详细</span><span class="sxs-lookup"><span data-stu-id="1a2eb-109">Verbose</span></span>|  
|<span data-ttu-id="1a2eb-110">通道</span><span class="sxs-lookup"><span data-stu-id="1a2eb-110">Channel</span></span>|<span data-ttu-id="1a2eb-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1a2eb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1a2eb-112">描述</span><span class="sxs-lookup"><span data-stu-id="1a2eb-112">Description</span></span>  
 <span data-ttu-id="1a2eb-113">指示已安排 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="1a2eb-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1a2eb-114">消息</span><span class="sxs-lookup"><span data-stu-id="1a2eb-114">Message</span></span>  
 <span data-ttu-id="1a2eb-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="1a2eb-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1a2eb-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1a2eb-116">Details</span></span>  
  
|<span data-ttu-id="1a2eb-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1a2eb-117">Data Item Name</span></span>|<span data-ttu-id="1a2eb-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1a2eb-118">Data Item Type</span></span>|<span data-ttu-id="1a2eb-119">描述</span><span class="sxs-lookup"><span data-stu-id="1a2eb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1a2eb-120">Activity</span><span class="sxs-lookup"><span data-stu-id="1a2eb-120">Activity</span></span>|<span data-ttu-id="1a2eb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1a2eb-121">xs:string</span></span>|<span data-ttu-id="1a2eb-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1a2eb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="1a2eb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1a2eb-123">DisplayName</span></span>|<span data-ttu-id="1a2eb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1a2eb-124">xs:string</span></span>|<span data-ttu-id="1a2eb-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1a2eb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="1a2eb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1a2eb-126">InstanceId</span></span>|<span data-ttu-id="1a2eb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1a2eb-127">xs:string</span></span>|<span data-ttu-id="1a2eb-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1a2eb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1a2eb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1a2eb-129">AppDomain</span></span>|<span data-ttu-id="1a2eb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1a2eb-130">xs:string</span></span>|<span data-ttu-id="1a2eb-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1a2eb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
