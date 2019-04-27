---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924834"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="2ae13-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="2ae13-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="2ae13-103">属性</span><span class="sxs-lookup"><span data-stu-id="2ae13-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ae13-104">Id</span><span class="sxs-lookup"><span data-stu-id="2ae13-104">ID</span></span>|<span data-ttu-id="2ae13-105">1036</span><span class="sxs-lookup"><span data-stu-id="2ae13-105">1036</span></span>|  
|<span data-ttu-id="2ae13-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2ae13-106">Keywords</span></span>|<span data-ttu-id="2ae13-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2ae13-107">WFRuntime</span></span>|  
|<span data-ttu-id="2ae13-108">级别</span><span class="sxs-lookup"><span data-stu-id="2ae13-108">Level</span></span>|<span data-ttu-id="2ae13-109">详细</span><span class="sxs-lookup"><span data-stu-id="2ae13-109">Verbose</span></span>|  
|<span data-ttu-id="2ae13-110">通道</span><span class="sxs-lookup"><span data-stu-id="2ae13-110">Channel</span></span>|<span data-ttu-id="2ae13-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="2ae13-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2ae13-112">描述</span><span class="sxs-lookup"><span data-stu-id="2ae13-112">Description</span></span>  
 <span data-ttu-id="2ae13-113">指示活动已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="2ae13-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2ae13-114">消息</span><span class="sxs-lookup"><span data-stu-id="2ae13-114">Message</span></span>  
 <span data-ttu-id="2ae13-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="2ae13-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2ae13-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="2ae13-116">Details</span></span>  
  
|<span data-ttu-id="2ae13-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2ae13-117">Data Item Name</span></span>|<span data-ttu-id="2ae13-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2ae13-118">Data Item Type</span></span>|<span data-ttu-id="2ae13-119">描述</span><span class="sxs-lookup"><span data-stu-id="2ae13-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2ae13-120">活动</span><span class="sxs-lookup"><span data-stu-id="2ae13-120">Activity</span></span>|<span data-ttu-id="2ae13-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae13-121">xs:string</span></span>|<span data-ttu-id="2ae13-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="2ae13-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="2ae13-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2ae13-123">DisplayName</span></span>|<span data-ttu-id="2ae13-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae13-124">xs:string</span></span>|<span data-ttu-id="2ae13-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2ae13-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="2ae13-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2ae13-126">InstanceId</span></span>|<span data-ttu-id="2ae13-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae13-127">xs:string</span></span>|<span data-ttu-id="2ae13-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="2ae13-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2ae13-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="2ae13-129">AppDomain</span></span>|<span data-ttu-id="2ae13-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae13-130">xs:string</span></span>|<span data-ttu-id="2ae13-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ae13-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
