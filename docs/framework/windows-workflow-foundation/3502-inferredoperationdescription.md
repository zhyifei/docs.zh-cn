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
ms.openlocfilehash: 144ab1a4a2fd313dc7817846e3e0118145cd3f8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="8cd5e-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="8cd5e-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="8cd5e-103">属性</span><span class="sxs-lookup"><span data-stu-id="8cd5e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cd5e-104">ID</span><span class="sxs-lookup"><span data-stu-id="8cd5e-104">ID</span></span>|<span data-ttu-id="8cd5e-105">3502</span><span class="sxs-lookup"><span data-stu-id="8cd5e-105">3502</span></span>|  
|<span data-ttu-id="8cd5e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8cd5e-106">Keywords</span></span>|<span data-ttu-id="8cd5e-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="8cd5e-107">WFServices</span></span>|  
|<span data-ttu-id="8cd5e-108">级别</span><span class="sxs-lookup"><span data-stu-id="8cd5e-108">Level</span></span>|<span data-ttu-id="8cd5e-109">信息</span><span class="sxs-lookup"><span data-stu-id="8cd5e-109">Information</span></span>|  
|<span data-ttu-id="8cd5e-110">通道</span><span class="sxs-lookup"><span data-stu-id="8cd5e-110">Channel</span></span>|<span data-ttu-id="8cd5e-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="8cd5e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8cd5e-112">描述</span><span class="sxs-lookup"><span data-stu-id="8cd5e-112">Description</span></span>  
 <span data-ttu-id="8cd5e-113">指示已从 WorkflowService 中推断出 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8cd5e-114">消息</span><span class="sxs-lookup"><span data-stu-id="8cd5e-114">Message</span></span>  
 <span data-ttu-id="8cd5e-115">已从 WorkflowService 中推断出协定“%2”中含有 Name='%1' 的 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="8cd5e-116">IsOneWay=%3。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8cd5e-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="8cd5e-117">Details</span></span>  
  
|<span data-ttu-id="8cd5e-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8cd5e-118">Data Item Name</span></span>|<span data-ttu-id="8cd5e-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8cd5e-119">Data Item Type</span></span>|<span data-ttu-id="8cd5e-120">描述</span><span class="sxs-lookup"><span data-stu-id="8cd5e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8cd5e-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="8cd5e-121">OperationName</span></span>|<span data-ttu-id="8cd5e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cd5e-122">xs:string</span></span>|<span data-ttu-id="8cd5e-123">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-123">The name of the operation.</span></span>|  
|<span data-ttu-id="8cd5e-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="8cd5e-124">ContractName</span></span>|<span data-ttu-id="8cd5e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cd5e-125">xs:string</span></span>|<span data-ttu-id="8cd5e-126">协定的名称。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-126">The name of the contract.</span></span>|  
|<span data-ttu-id="8cd5e-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="8cd5e-127">IsOneWay</span></span>|<span data-ttu-id="8cd5e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cd5e-128">xs:string</span></span>|<span data-ttu-id="8cd5e-129">true 或 false 指示协定是否为单向。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="8cd5e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8cd5e-130">AppDomain</span></span>|<span data-ttu-id="8cd5e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cd5e-131">xs:string</span></span>|<span data-ttu-id="8cd5e-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
