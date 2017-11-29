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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 044d67bc2b721451ade04947484899266d288d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="21da8-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="21da8-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="21da8-103">属性</span><span class="sxs-lookup"><span data-stu-id="21da8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21da8-104">ID</span><span class="sxs-lookup"><span data-stu-id="21da8-104">ID</span></span>|<span data-ttu-id="21da8-105">3502</span><span class="sxs-lookup"><span data-stu-id="21da8-105">3502</span></span>|  
|<span data-ttu-id="21da8-106">关键字</span><span class="sxs-lookup"><span data-stu-id="21da8-106">Keywords</span></span>|<span data-ttu-id="21da8-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="21da8-107">WFServices</span></span>|  
|<span data-ttu-id="21da8-108">级别</span><span class="sxs-lookup"><span data-stu-id="21da8-108">Level</span></span>|<span data-ttu-id="21da8-109">信息</span><span class="sxs-lookup"><span data-stu-id="21da8-109">Information</span></span>|  
|<span data-ttu-id="21da8-110">通道</span><span class="sxs-lookup"><span data-stu-id="21da8-110">Channel</span></span>|<span data-ttu-id="21da8-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="21da8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="21da8-112">描述</span><span class="sxs-lookup"><span data-stu-id="21da8-112">Description</span></span>  
 <span data-ttu-id="21da8-113">指示已从 WorkflowService 中推断出 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="21da8-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="21da8-114">消息</span><span class="sxs-lookup"><span data-stu-id="21da8-114">Message</span></span>  
 <span data-ttu-id="21da8-115">已从 WorkflowService 中推断出协定“%2”中含有 Name='%1' 的 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="21da8-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="21da8-116">IsOneWay=%3。</span><span class="sxs-lookup"><span data-stu-id="21da8-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="21da8-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="21da8-117">Details</span></span>  
  
|<span data-ttu-id="21da8-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="21da8-118">Data Item Name</span></span>|<span data-ttu-id="21da8-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="21da8-119">Data Item Type</span></span>|<span data-ttu-id="21da8-120">描述</span><span class="sxs-lookup"><span data-stu-id="21da8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="21da8-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="21da8-121">OperationName</span></span>|<span data-ttu-id="21da8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="21da8-122">xs:string</span></span>|<span data-ttu-id="21da8-123">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="21da8-123">The name of the operation.</span></span>|  
|<span data-ttu-id="21da8-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="21da8-124">ContractName</span></span>|<span data-ttu-id="21da8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="21da8-125">xs:string</span></span>|<span data-ttu-id="21da8-126">协定的名称。</span><span class="sxs-lookup"><span data-stu-id="21da8-126">The name of the contract.</span></span>|  
|<span data-ttu-id="21da8-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="21da8-127">IsOneWay</span></span>|<span data-ttu-id="21da8-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="21da8-128">xs:string</span></span>|<span data-ttu-id="21da8-129">true 或 false 指示协定是否为单向。</span><span class="sxs-lookup"><span data-stu-id="21da8-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="21da8-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="21da8-130">AppDomain</span></span>|<span data-ttu-id="21da8-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="21da8-131">xs:string</span></span>|<span data-ttu-id="21da8-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="21da8-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
