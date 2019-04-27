---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924626"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="45f81-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="45f81-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="45f81-103">属性</span><span class="sxs-lookup"><span data-stu-id="45f81-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45f81-104">Id</span><span class="sxs-lookup"><span data-stu-id="45f81-104">ID</span></span>|<span data-ttu-id="45f81-105">1026</span><span class="sxs-lookup"><span data-stu-id="45f81-105">1026</span></span>|  
|<span data-ttu-id="45f81-106">关键字</span><span class="sxs-lookup"><span data-stu-id="45f81-106">Keywords</span></span>|<span data-ttu-id="45f81-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="45f81-107">WFRuntime</span></span>|  
|<span data-ttu-id="45f81-108">级别</span><span class="sxs-lookup"><span data-stu-id="45f81-108">Level</span></span>|<span data-ttu-id="45f81-109">详细</span><span class="sxs-lookup"><span data-stu-id="45f81-109">Verbose</span></span>|  
|<span data-ttu-id="45f81-110">通道</span><span class="sxs-lookup"><span data-stu-id="45f81-110">Channel</span></span>|<span data-ttu-id="45f81-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="45f81-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45f81-112">描述</span><span class="sxs-lookup"><span data-stu-id="45f81-112">Description</span></span>  
 <span data-ttu-id="45f81-113">指示已安排 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="45f81-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45f81-114">消息</span><span class="sxs-lookup"><span data-stu-id="45f81-114">Message</span></span>  
 <span data-ttu-id="45f81-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="45f81-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45f81-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="45f81-116">Details</span></span>  
  
|<span data-ttu-id="45f81-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="45f81-117">Data Item Name</span></span>|<span data-ttu-id="45f81-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="45f81-118">Data Item Type</span></span>|<span data-ttu-id="45f81-119">描述</span><span class="sxs-lookup"><span data-stu-id="45f81-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45f81-120">活动</span><span class="sxs-lookup"><span data-stu-id="45f81-120">Activity</span></span>|<span data-ttu-id="45f81-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="45f81-121">xs:string</span></span>|<span data-ttu-id="45f81-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="45f81-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="45f81-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="45f81-123">DisplayName</span></span>|<span data-ttu-id="45f81-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="45f81-124">xs:string</span></span>|<span data-ttu-id="45f81-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="45f81-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="45f81-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="45f81-126">InstanceId</span></span>|<span data-ttu-id="45f81-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="45f81-127">xs:string</span></span>|<span data-ttu-id="45f81-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="45f81-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="45f81-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="45f81-129">AppDomain</span></span>|<span data-ttu-id="45f81-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="45f81-130">xs:string</span></span>|<span data-ttu-id="45f81-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="45f81-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
