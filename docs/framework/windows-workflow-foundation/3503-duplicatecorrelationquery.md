---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755592"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="e94f8-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="e94f8-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="e94f8-103">属性</span><span class="sxs-lookup"><span data-stu-id="e94f8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e94f8-104">Id</span><span class="sxs-lookup"><span data-stu-id="e94f8-104">ID</span></span>|<span data-ttu-id="e94f8-105">3503</span><span class="sxs-lookup"><span data-stu-id="e94f8-105">3503</span></span>|  
|<span data-ttu-id="e94f8-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e94f8-106">Keywords</span></span>|<span data-ttu-id="e94f8-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="e94f8-107">WFServices</span></span>|  
|<span data-ttu-id="e94f8-108">级别</span><span class="sxs-lookup"><span data-stu-id="e94f8-108">Level</span></span>|<span data-ttu-id="e94f8-109">警告</span><span class="sxs-lookup"><span data-stu-id="e94f8-109">Warning</span></span>|  
|<span data-ttu-id="e94f8-110">通道</span><span class="sxs-lookup"><span data-stu-id="e94f8-110">Channel</span></span>|<span data-ttu-id="e94f8-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="e94f8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e94f8-112">描述</span><span class="sxs-lookup"><span data-stu-id="e94f8-112">Description</span></span>  
 <span data-ttu-id="e94f8-113">指示找到了重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="e94f8-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="e94f8-114">计算相关性时将不使用重复查询。</span><span class="sxs-lookup"><span data-stu-id="e94f8-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e94f8-115">消息</span><span class="sxs-lookup"><span data-stu-id="e94f8-115">Message</span></span>  
 <span data-ttu-id="e94f8-116">找到了含有 Where='%1' 的重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="e94f8-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="e94f8-117">计算相关性时将不使用此重复查询。</span><span class="sxs-lookup"><span data-stu-id="e94f8-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e94f8-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="e94f8-118">Details</span></span>  
  
|<span data-ttu-id="e94f8-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e94f8-119">Data Item Name</span></span>|<span data-ttu-id="e94f8-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e94f8-120">Data Item Type</span></span>|<span data-ttu-id="e94f8-121">描述</span><span class="sxs-lookup"><span data-stu-id="e94f8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e94f8-122">Where</span><span class="sxs-lookup"><span data-stu-id="e94f8-122">Where</span></span>|<span data-ttu-id="e94f8-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e94f8-123">xs:string</span></span>|<span data-ttu-id="e94f8-124">相关查询的 Where 部分。</span><span class="sxs-lookup"><span data-stu-id="e94f8-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="e94f8-125">应用程序域</span><span class="sxs-lookup"><span data-stu-id="e94f8-125">AppDomain</span></span>|<span data-ttu-id="e94f8-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e94f8-126">xs:string</span></span>|<span data-ttu-id="e94f8-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e94f8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
