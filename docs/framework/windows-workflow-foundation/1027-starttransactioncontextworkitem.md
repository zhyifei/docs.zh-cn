---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: 231a7607f2ce9a38e8dd6c1486a68bc9eb459e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510804"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="b7f75-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="b7f75-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b7f75-103">属性</span><span class="sxs-lookup"><span data-stu-id="b7f75-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7f75-104">ID</span><span class="sxs-lookup"><span data-stu-id="b7f75-104">ID</span></span>|<span data-ttu-id="b7f75-105">1027</span><span class="sxs-lookup"><span data-stu-id="b7f75-105">1027</span></span>|  
|<span data-ttu-id="b7f75-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b7f75-106">Keywords</span></span>|<span data-ttu-id="b7f75-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b7f75-107">WFRuntime</span></span>|  
|<span data-ttu-id="b7f75-108">级别</span><span class="sxs-lookup"><span data-stu-id="b7f75-108">Level</span></span>|<span data-ttu-id="b7f75-109">详细</span><span class="sxs-lookup"><span data-stu-id="b7f75-109">Verbose</span></span>|  
|<span data-ttu-id="b7f75-110">通道</span><span class="sxs-lookup"><span data-stu-id="b7f75-110">Channel</span></span>|<span data-ttu-id="b7f75-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b7f75-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b7f75-112">描述</span><span class="sxs-lookup"><span data-stu-id="b7f75-112">Description</span></span>  
 <span data-ttu-id="b7f75-113">指示 TransactionContextWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="b7f75-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b7f75-114">消息</span><span class="sxs-lookup"><span data-stu-id="b7f75-114">Message</span></span>  
 <span data-ttu-id="b7f75-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="b7f75-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b7f75-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="b7f75-116">Details</span></span>  
  
|<span data-ttu-id="b7f75-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b7f75-117">Data Item Name</span></span>|<span data-ttu-id="b7f75-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b7f75-118">Data Item Type</span></span>|<span data-ttu-id="b7f75-119">描述</span><span class="sxs-lookup"><span data-stu-id="b7f75-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b7f75-120">Activity</span><span class="sxs-lookup"><span data-stu-id="b7f75-120">Activity</span></span>|<span data-ttu-id="b7f75-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7f75-121">xs:string</span></span>|<span data-ttu-id="b7f75-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="b7f75-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b7f75-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b7f75-123">DisplayName</span></span>|<span data-ttu-id="b7f75-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7f75-124">xs:string</span></span>|<span data-ttu-id="b7f75-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b7f75-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b7f75-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b7f75-126">InstanceId</span></span>|<span data-ttu-id="b7f75-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7f75-127">xs:string</span></span>|<span data-ttu-id="b7f75-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b7f75-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b7f75-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b7f75-129">AppDomain</span></span>|<span data-ttu-id="b7f75-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7f75-130">xs:string</span></span>|<span data-ttu-id="b7f75-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b7f75-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
