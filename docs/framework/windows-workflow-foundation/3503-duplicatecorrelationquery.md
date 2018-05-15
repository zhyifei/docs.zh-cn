---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="f87d2-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="f87d2-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="f87d2-103">属性</span><span class="sxs-lookup"><span data-stu-id="f87d2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f87d2-104">ID</span><span class="sxs-lookup"><span data-stu-id="f87d2-104">ID</span></span>|<span data-ttu-id="f87d2-105">3503</span><span class="sxs-lookup"><span data-stu-id="f87d2-105">3503</span></span>|  
|<span data-ttu-id="f87d2-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f87d2-106">Keywords</span></span>|<span data-ttu-id="f87d2-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f87d2-107">WFServices</span></span>|  
|<span data-ttu-id="f87d2-108">级别</span><span class="sxs-lookup"><span data-stu-id="f87d2-108">Level</span></span>|<span data-ttu-id="f87d2-109">警告</span><span class="sxs-lookup"><span data-stu-id="f87d2-109">Warning</span></span>|  
|<span data-ttu-id="f87d2-110">通道</span><span class="sxs-lookup"><span data-stu-id="f87d2-110">Channel</span></span>|<span data-ttu-id="f87d2-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="f87d2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f87d2-112">描述</span><span class="sxs-lookup"><span data-stu-id="f87d2-112">Description</span></span>  
 <span data-ttu-id="f87d2-113">指示找到了重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="f87d2-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="f87d2-114">计算相关性时将不使用重复查询。</span><span class="sxs-lookup"><span data-stu-id="f87d2-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f87d2-115">消息</span><span class="sxs-lookup"><span data-stu-id="f87d2-115">Message</span></span>  
 <span data-ttu-id="f87d2-116">找到了含有 Where='%1' 的重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="f87d2-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="f87d2-117">计算相关性时将不使用此重复查询。</span><span class="sxs-lookup"><span data-stu-id="f87d2-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f87d2-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="f87d2-118">Details</span></span>  
  
|<span data-ttu-id="f87d2-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f87d2-119">Data Item Name</span></span>|<span data-ttu-id="f87d2-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f87d2-120">Data Item Type</span></span>|<span data-ttu-id="f87d2-121">描述</span><span class="sxs-lookup"><span data-stu-id="f87d2-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f87d2-122">Where</span><span class="sxs-lookup"><span data-stu-id="f87d2-122">Where</span></span>|<span data-ttu-id="f87d2-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f87d2-123">xs:string</span></span>|<span data-ttu-id="f87d2-124">相关查询的 Where 部分。</span><span class="sxs-lookup"><span data-stu-id="f87d2-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="f87d2-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f87d2-125">AppDomain</span></span>|<span data-ttu-id="f87d2-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f87d2-126">xs:string</span></span>|<span data-ttu-id="f87d2-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f87d2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
