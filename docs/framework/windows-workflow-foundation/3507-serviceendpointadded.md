---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: c787a1a5af752a3d08e2049cfa0b600b7739e56c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="9daa4-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="9daa4-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="9daa4-103">属性</span><span class="sxs-lookup"><span data-stu-id="9daa4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9daa4-104">ID</span><span class="sxs-lookup"><span data-stu-id="9daa4-104">ID</span></span>|<span data-ttu-id="9daa4-105">3507</span><span class="sxs-lookup"><span data-stu-id="9daa4-105">3507</span></span>|  
|<span data-ttu-id="9daa4-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9daa4-106">Keywords</span></span>|<span data-ttu-id="9daa4-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="9daa4-107">WFServices</span></span>|  
|<span data-ttu-id="9daa4-108">级别</span><span class="sxs-lookup"><span data-stu-id="9daa4-108">Level</span></span>|<span data-ttu-id="9daa4-109">信息</span><span class="sxs-lookup"><span data-stu-id="9daa4-109">Information</span></span>|  
|<span data-ttu-id="9daa4-110">通道</span><span class="sxs-lookup"><span data-stu-id="9daa4-110">Channel</span></span>|<span data-ttu-id="9daa4-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="9daa4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9daa4-112">描述</span><span class="sxs-lookup"><span data-stu-id="9daa4-112">Description</span></span>  
 <span data-ttu-id="9daa4-113">指示添加了服务终结点。</span><span class="sxs-lookup"><span data-stu-id="9daa4-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9daa4-114">消息</span><span class="sxs-lookup"><span data-stu-id="9daa4-114">Message</span></span>  
 <span data-ttu-id="9daa4-115">已为地址“%1”、绑定“%2”和协定“%3”添加了服务终结点。</span><span class="sxs-lookup"><span data-stu-id="9daa4-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9daa4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9daa4-116">Details</span></span>  
  
|<span data-ttu-id="9daa4-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9daa4-117">Data Item Name</span></span>|<span data-ttu-id="9daa4-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9daa4-118">Data Item Type</span></span>|<span data-ttu-id="9daa4-119">描述</span><span class="sxs-lookup"><span data-stu-id="9daa4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9daa4-120">Address</span><span class="sxs-lookup"><span data-stu-id="9daa4-120">Address</span></span>|<span data-ttu-id="9daa4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa4-121">xs:string</span></span>|<span data-ttu-id="9daa4-122">终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="9daa4-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="9daa4-123">绑定</span><span class="sxs-lookup"><span data-stu-id="9daa4-123">Binding</span></span>|<span data-ttu-id="9daa4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa4-124">xs:string</span></span>|<span data-ttu-id="9daa4-125">终结点的绑定。</span><span class="sxs-lookup"><span data-stu-id="9daa4-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="9daa4-126">协定</span><span class="sxs-lookup"><span data-stu-id="9daa4-126">Contract</span></span>|<span data-ttu-id="9daa4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa4-127">xs:string</span></span>|<span data-ttu-id="9daa4-128">终结点的协定。</span><span class="sxs-lookup"><span data-stu-id="9daa4-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="9daa4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9daa4-129">AppDomain</span></span>|<span data-ttu-id="9daa4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9daa4-130">xs:string</span></span>|<span data-ttu-id="9daa4-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9daa4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
