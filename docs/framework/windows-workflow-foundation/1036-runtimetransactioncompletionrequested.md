---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510388"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="57d2c-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="57d2c-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="57d2c-103">属性</span><span class="sxs-lookup"><span data-stu-id="57d2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57d2c-104">ID</span><span class="sxs-lookup"><span data-stu-id="57d2c-104">ID</span></span>|<span data-ttu-id="57d2c-105">1036</span><span class="sxs-lookup"><span data-stu-id="57d2c-105">1036</span></span>|  
|<span data-ttu-id="57d2c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="57d2c-106">Keywords</span></span>|<span data-ttu-id="57d2c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="57d2c-107">WFRuntime</span></span>|  
|<span data-ttu-id="57d2c-108">级别</span><span class="sxs-lookup"><span data-stu-id="57d2c-108">Level</span></span>|<span data-ttu-id="57d2c-109">详细</span><span class="sxs-lookup"><span data-stu-id="57d2c-109">Verbose</span></span>|  
|<span data-ttu-id="57d2c-110">通道</span><span class="sxs-lookup"><span data-stu-id="57d2c-110">Channel</span></span>|<span data-ttu-id="57d2c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="57d2c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="57d2c-112">描述</span><span class="sxs-lookup"><span data-stu-id="57d2c-112">Description</span></span>  
 <span data-ttu-id="57d2c-113">指示活动已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="57d2c-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="57d2c-114">消息</span><span class="sxs-lookup"><span data-stu-id="57d2c-114">Message</span></span>  
 <span data-ttu-id="57d2c-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="57d2c-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="57d2c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="57d2c-116">Details</span></span>  
  
|<span data-ttu-id="57d2c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="57d2c-117">Data Item Name</span></span>|<span data-ttu-id="57d2c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="57d2c-118">Data Item Type</span></span>|<span data-ttu-id="57d2c-119">描述</span><span class="sxs-lookup"><span data-stu-id="57d2c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="57d2c-120">Activity</span><span class="sxs-lookup"><span data-stu-id="57d2c-120">Activity</span></span>|<span data-ttu-id="57d2c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="57d2c-121">xs:string</span></span>|<span data-ttu-id="57d2c-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="57d2c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="57d2c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="57d2c-123">DisplayName</span></span>|<span data-ttu-id="57d2c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="57d2c-124">xs:string</span></span>|<span data-ttu-id="57d2c-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="57d2c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="57d2c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="57d2c-126">InstanceId</span></span>|<span data-ttu-id="57d2c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="57d2c-127">xs:string</span></span>|<span data-ttu-id="57d2c-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="57d2c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="57d2c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="57d2c-129">AppDomain</span></span>|<span data-ttu-id="57d2c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="57d2c-130">xs:string</span></span>|<span data-ttu-id="57d2c-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="57d2c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
