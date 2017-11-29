---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60367b33e1e57cce8646b4fcde79c7d4fd20a4cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="ea965-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="ea965-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="ea965-103">属性</span><span class="sxs-lookup"><span data-stu-id="ea965-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea965-104">ID</span><span class="sxs-lookup"><span data-stu-id="ea965-104">ID</span></span>|<span data-ttu-id="ea965-105">3503</span><span class="sxs-lookup"><span data-stu-id="ea965-105">3503</span></span>|  
|<span data-ttu-id="ea965-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ea965-106">Keywords</span></span>|<span data-ttu-id="ea965-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ea965-107">WFServices</span></span>|  
|<span data-ttu-id="ea965-108">级别</span><span class="sxs-lookup"><span data-stu-id="ea965-108">Level</span></span>|<span data-ttu-id="ea965-109">警告</span><span class="sxs-lookup"><span data-stu-id="ea965-109">Warning</span></span>|  
|<span data-ttu-id="ea965-110">通道</span><span class="sxs-lookup"><span data-stu-id="ea965-110">Channel</span></span>|<span data-ttu-id="ea965-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="ea965-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ea965-112">描述</span><span class="sxs-lookup"><span data-stu-id="ea965-112">Description</span></span>  
 <span data-ttu-id="ea965-113">指示找到了重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="ea965-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="ea965-114">计算相关性时将不使用重复查询。</span><span class="sxs-lookup"><span data-stu-id="ea965-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ea965-115">消息</span><span class="sxs-lookup"><span data-stu-id="ea965-115">Message</span></span>  
 <span data-ttu-id="ea965-116">找到了含有 Where='%1' 的重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="ea965-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="ea965-117">计算相关性时将不使用此重复查询。</span><span class="sxs-lookup"><span data-stu-id="ea965-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ea965-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="ea965-118">Details</span></span>  
  
|<span data-ttu-id="ea965-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ea965-119">Data Item Name</span></span>|<span data-ttu-id="ea965-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ea965-120">Data Item Type</span></span>|<span data-ttu-id="ea965-121">描述</span><span class="sxs-lookup"><span data-stu-id="ea965-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ea965-122">Where</span><span class="sxs-lookup"><span data-stu-id="ea965-122">Where</span></span>|<span data-ttu-id="ea965-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea965-123">xs:string</span></span>|<span data-ttu-id="ea965-124">相关查询的 Where 部分。</span><span class="sxs-lookup"><span data-stu-id="ea965-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="ea965-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ea965-125">AppDomain</span></span>|<span data-ttu-id="ea965-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea965-126">xs:string</span></span>|<span data-ttu-id="ea965-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ea965-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
