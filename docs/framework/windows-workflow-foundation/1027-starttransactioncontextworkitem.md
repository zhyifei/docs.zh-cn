---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: 231a7607f2ce9a38e8dd6c1486a68bc9eb459e5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008819"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="4f3db-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="4f3db-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4f3db-103">属性</span><span class="sxs-lookup"><span data-stu-id="4f3db-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f3db-104">Id</span><span class="sxs-lookup"><span data-stu-id="4f3db-104">ID</span></span>|<span data-ttu-id="4f3db-105">1027</span><span class="sxs-lookup"><span data-stu-id="4f3db-105">1027</span></span>|  
|<span data-ttu-id="4f3db-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4f3db-106">Keywords</span></span>|<span data-ttu-id="4f3db-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4f3db-107">WFRuntime</span></span>|  
|<span data-ttu-id="4f3db-108">级别</span><span class="sxs-lookup"><span data-stu-id="4f3db-108">Level</span></span>|<span data-ttu-id="4f3db-109">详细</span><span class="sxs-lookup"><span data-stu-id="4f3db-109">Verbose</span></span>|  
|<span data-ttu-id="4f3db-110">通道</span><span class="sxs-lookup"><span data-stu-id="4f3db-110">Channel</span></span>|<span data-ttu-id="4f3db-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4f3db-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4f3db-112">描述</span><span class="sxs-lookup"><span data-stu-id="4f3db-112">Description</span></span>  
 <span data-ttu-id="4f3db-113">指示 TransactionContextWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="4f3db-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4f3db-114">消息</span><span class="sxs-lookup"><span data-stu-id="4f3db-114">Message</span></span>  
 <span data-ttu-id="4f3db-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="4f3db-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4f3db-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4f3db-116">Details</span></span>  
  
|<span data-ttu-id="4f3db-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4f3db-117">Data Item Name</span></span>|<span data-ttu-id="4f3db-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4f3db-118">Data Item Type</span></span>|<span data-ttu-id="4f3db-119">描述</span><span class="sxs-lookup"><span data-stu-id="4f3db-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4f3db-120">活动</span><span class="sxs-lookup"><span data-stu-id="4f3db-120">Activity</span></span>|<span data-ttu-id="4f3db-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f3db-121">xs:string</span></span>|<span data-ttu-id="4f3db-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="4f3db-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4f3db-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4f3db-123">DisplayName</span></span>|<span data-ttu-id="4f3db-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f3db-124">xs:string</span></span>|<span data-ttu-id="4f3db-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4f3db-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4f3db-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4f3db-126">InstanceId</span></span>|<span data-ttu-id="4f3db-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f3db-127">xs:string</span></span>|<span data-ttu-id="4f3db-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="4f3db-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4f3db-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="4f3db-129">AppDomain</span></span>|<span data-ttu-id="4f3db-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f3db-130">xs:string</span></span>|<span data-ttu-id="4f3db-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4f3db-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
