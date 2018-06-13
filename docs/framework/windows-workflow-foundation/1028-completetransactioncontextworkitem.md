---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511382"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="b63d4-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="b63d4-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b63d4-103">属性</span><span class="sxs-lookup"><span data-stu-id="b63d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b63d4-104">ID</span><span class="sxs-lookup"><span data-stu-id="b63d4-104">ID</span></span>|<span data-ttu-id="b63d4-105">1028</span><span class="sxs-lookup"><span data-stu-id="b63d4-105">1028</span></span>|  
|<span data-ttu-id="b63d4-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b63d4-106">Keywords</span></span>|<span data-ttu-id="b63d4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b63d4-107">WFRuntime</span></span>|  
|<span data-ttu-id="b63d4-108">级别</span><span class="sxs-lookup"><span data-stu-id="b63d4-108">Level</span></span>|<span data-ttu-id="b63d4-109">详细</span><span class="sxs-lookup"><span data-stu-id="b63d4-109">Verbose</span></span>|  
|<span data-ttu-id="b63d4-110">通道</span><span class="sxs-lookup"><span data-stu-id="b63d4-110">Channel</span></span>|<span data-ttu-id="b63d4-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b63d4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b63d4-112">描述</span><span class="sxs-lookup"><span data-stu-id="b63d4-112">Description</span></span>  
 <span data-ttu-id="b63d4-113">指示 TransactionContextWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="b63d4-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b63d4-114">消息</span><span class="sxs-lookup"><span data-stu-id="b63d4-114">Message</span></span>  
 <span data-ttu-id="b63d4-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 TransactionContextWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="b63d4-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b63d4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="b63d4-116">Details</span></span>  
  
|<span data-ttu-id="b63d4-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b63d4-117">Data Item Name</span></span>|<span data-ttu-id="b63d4-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b63d4-118">Data Item Type</span></span>|<span data-ttu-id="b63d4-119">描述</span><span class="sxs-lookup"><span data-stu-id="b63d4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b63d4-120">Activity</span><span class="sxs-lookup"><span data-stu-id="b63d4-120">Activity</span></span>|<span data-ttu-id="b63d4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b63d4-121">xs:string</span></span>|<span data-ttu-id="b63d4-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="b63d4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b63d4-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b63d4-123">DisplayName</span></span>|<span data-ttu-id="b63d4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b63d4-124">xs:string</span></span>|<span data-ttu-id="b63d4-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b63d4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b63d4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b63d4-126">InstanceId</span></span>|<span data-ttu-id="b63d4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b63d4-127">xs:string</span></span>|<span data-ttu-id="b63d4-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b63d4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b63d4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b63d4-129">AppDomain</span></span>|<span data-ttu-id="b63d4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b63d4-130">xs:string</span></span>|<span data-ttu-id="b63d4-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b63d4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
