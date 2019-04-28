---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924431"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="ab625-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="ab625-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ab625-103">属性</span><span class="sxs-lookup"><span data-stu-id="ab625-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab625-104">Id</span><span class="sxs-lookup"><span data-stu-id="ab625-104">ID</span></span>|<span data-ttu-id="ab625-105">1019</span><span class="sxs-lookup"><span data-stu-id="ab625-105">1019</span></span>|  
|<span data-ttu-id="ab625-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ab625-106">Keywords</span></span>|<span data-ttu-id="ab625-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ab625-107">WFRuntime</span></span>|  
|<span data-ttu-id="ab625-108">级别</span><span class="sxs-lookup"><span data-stu-id="ab625-108">Level</span></span>|<span data-ttu-id="ab625-109">详细</span><span class="sxs-lookup"><span data-stu-id="ab625-109">Verbose</span></span>|  
|<span data-ttu-id="ab625-110">通道</span><span class="sxs-lookup"><span data-stu-id="ab625-110">Channel</span></span>|<span data-ttu-id="ab625-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="ab625-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ab625-112">描述</span><span class="sxs-lookup"><span data-stu-id="ab625-112">Description</span></span>  
 <span data-ttu-id="ab625-113">指示 CancelActivityWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="ab625-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ab625-114">消息</span><span class="sxs-lookup"><span data-stu-id="ab625-114">Message</span></span>  
 <span data-ttu-id="ab625-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 CancelActivityWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="ab625-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ab625-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="ab625-116">Details</span></span>  
  
|<span data-ttu-id="ab625-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ab625-117">Data Item Name</span></span>|<span data-ttu-id="ab625-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ab625-118">Data Item Type</span></span>|<span data-ttu-id="ab625-119">描述</span><span class="sxs-lookup"><span data-stu-id="ab625-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ab625-120">活动</span><span class="sxs-lookup"><span data-stu-id="ab625-120">Activity</span></span>|<span data-ttu-id="ab625-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab625-121">xs:string</span></span>|<span data-ttu-id="ab625-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ab625-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ab625-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ab625-123">DisplayName</span></span>|<span data-ttu-id="ab625-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab625-124">xs:string</span></span>|<span data-ttu-id="ab625-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ab625-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ab625-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ab625-126">InstanceId</span></span>|<span data-ttu-id="ab625-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab625-127">xs:string</span></span>|<span data-ttu-id="ab625-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ab625-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ab625-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="ab625-129">AppDomain</span></span>|<span data-ttu-id="ab625-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab625-130">xs:string</span></span>|<span data-ttu-id="ab625-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ab625-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
