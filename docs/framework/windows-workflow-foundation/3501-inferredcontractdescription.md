---
title: 3501 - InferredContractDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d8f5b5380b2167c6a168278f1242bfbf5e7a8fbc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3501---inferredcontractdescription"></a><span data-ttu-id="54a9a-102">3501 - InferredContractDescription</span><span class="sxs-lookup"><span data-stu-id="54a9a-102">3501 - InferredContractDescription</span></span>
## <a name="properties"></a><span data-ttu-id="54a9a-103">属性</span><span class="sxs-lookup"><span data-stu-id="54a9a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54a9a-104">ID</span><span class="sxs-lookup"><span data-stu-id="54a9a-104">ID</span></span>|<span data-ttu-id="54a9a-105">3501</span><span class="sxs-lookup"><span data-stu-id="54a9a-105">3501</span></span>|  
|<span data-ttu-id="54a9a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="54a9a-106">Keywords</span></span>|<span data-ttu-id="54a9a-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="54a9a-107">WFServices</span></span>|  
|<span data-ttu-id="54a9a-108">级别</span><span class="sxs-lookup"><span data-stu-id="54a9a-108">Level</span></span>|<span data-ttu-id="54a9a-109">信息</span><span class="sxs-lookup"><span data-stu-id="54a9a-109">Information</span></span>|  
|<span data-ttu-id="54a9a-110">通道</span><span class="sxs-lookup"><span data-stu-id="54a9a-110">Channel</span></span>|<span data-ttu-id="54a9a-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="54a9a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="54a9a-112">描述</span><span class="sxs-lookup"><span data-stu-id="54a9a-112">Description</span></span>  
 <span data-ttu-id="54a9a-113">指示已从 WorkflowService 中推断出 ContractDescription。</span><span class="sxs-lookup"><span data-stu-id="54a9a-113">Indicates a ContractDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="54a9a-114">消息</span><span class="sxs-lookup"><span data-stu-id="54a9a-114">Message</span></span>  
 <span data-ttu-id="54a9a-115">已从 WorkflowService 中推断出含有 Name 为“%1”和 Namespace 为“%2”的 ContractDescription。</span><span class="sxs-lookup"><span data-stu-id="54a9a-115">ContractDescription with Name='%1' and Namespace='%2' has been inferred from WorkflowService.</span></span>  
  
## <a name="details"></a><span data-ttu-id="54a9a-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="54a9a-116">Details</span></span>  
  
|<span data-ttu-id="54a9a-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="54a9a-117">Data Item Name</span></span>|<span data-ttu-id="54a9a-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="54a9a-118">Data Item Type</span></span>|<span data-ttu-id="54a9a-119">描述</span><span class="sxs-lookup"><span data-stu-id="54a9a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="54a9a-120">名称</span><span class="sxs-lookup"><span data-stu-id="54a9a-120">Name</span></span>|<span data-ttu-id="54a9a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="54a9a-121">xs:string</span></span>|<span data-ttu-id="54a9a-122">ContractDescription 的名称。</span><span class="sxs-lookup"><span data-stu-id="54a9a-122">The name of the ContractDescription.</span></span>|  
|<span data-ttu-id="54a9a-123">命名空间</span><span class="sxs-lookup"><span data-stu-id="54a9a-123">Namespace</span></span>|<span data-ttu-id="54a9a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="54a9a-124">xs:string</span></span>|<span data-ttu-id="54a9a-125">ContractDescription 的命名空间。</span><span class="sxs-lookup"><span data-stu-id="54a9a-125">The namespace of the ContractDescription.</span></span>|  
|<span data-ttu-id="54a9a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="54a9a-126">AppDomain</span></span>|<span data-ttu-id="54a9a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="54a9a-127">xs:string</span></span>|<span data-ttu-id="54a9a-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="54a9a-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
