---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2c2464cd8c6f0c16946847a5503270453d5b019
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="b98c7-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="b98c7-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="b98c7-103">属性</span><span class="sxs-lookup"><span data-stu-id="b98c7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b98c7-104">ID</span><span class="sxs-lookup"><span data-stu-id="b98c7-104">ID</span></span>|<span data-ttu-id="b98c7-105">3502</span><span class="sxs-lookup"><span data-stu-id="b98c7-105">3502</span></span>|  
|<span data-ttu-id="b98c7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b98c7-106">Keywords</span></span>|<span data-ttu-id="b98c7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="b98c7-107">WFServices</span></span>|  
|<span data-ttu-id="b98c7-108">级别</span><span class="sxs-lookup"><span data-stu-id="b98c7-108">Level</span></span>|<span data-ttu-id="b98c7-109">信息</span><span class="sxs-lookup"><span data-stu-id="b98c7-109">Information</span></span>|  
|<span data-ttu-id="b98c7-110">通道</span><span class="sxs-lookup"><span data-stu-id="b98c7-110">Channel</span></span>|<span data-ttu-id="b98c7-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="b98c7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b98c7-112">描述</span><span class="sxs-lookup"><span data-stu-id="b98c7-112">Description</span></span>  
 <span data-ttu-id="b98c7-113">指示已从 WorkflowService 中推断出 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="b98c7-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b98c7-114">消息</span><span class="sxs-lookup"><span data-stu-id="b98c7-114">Message</span></span>  
 <span data-ttu-id="b98c7-115">已从 WorkflowService 中推断出协定“%2”中含有 Name='%1' 的 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="b98c7-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="b98c7-116">IsOneWay=%3。</span><span class="sxs-lookup"><span data-stu-id="b98c7-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b98c7-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="b98c7-117">Details</span></span>  
  
|<span data-ttu-id="b98c7-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b98c7-118">Data Item Name</span></span>|<span data-ttu-id="b98c7-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b98c7-119">Data Item Type</span></span>|<span data-ttu-id="b98c7-120">描述</span><span class="sxs-lookup"><span data-stu-id="b98c7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b98c7-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="b98c7-121">OperationName</span></span>|<span data-ttu-id="b98c7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b98c7-122">xs:string</span></span>|<span data-ttu-id="b98c7-123">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="b98c7-123">The name of the operation.</span></span>|  
|<span data-ttu-id="b98c7-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="b98c7-124">ContractName</span></span>|<span data-ttu-id="b98c7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b98c7-125">xs:string</span></span>|<span data-ttu-id="b98c7-126">协定的名称。</span><span class="sxs-lookup"><span data-stu-id="b98c7-126">The name of the contract.</span></span>|  
|<span data-ttu-id="b98c7-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="b98c7-127">IsOneWay</span></span>|<span data-ttu-id="b98c7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b98c7-128">xs:string</span></span>|<span data-ttu-id="b98c7-129">true 或 false 指示协定是否为单向。</span><span class="sxs-lookup"><span data-stu-id="b98c7-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="b98c7-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b98c7-130">AppDomain</span></span>|<span data-ttu-id="b98c7-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b98c7-131">xs:string</span></span>|<span data-ttu-id="b98c7-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b98c7-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
