---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: c787a1a5af752a3d08e2049cfa0b600b7739e56c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009833"
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="5a260-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="5a260-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="5a260-103">属性</span><span class="sxs-lookup"><span data-stu-id="5a260-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a260-104">Id</span><span class="sxs-lookup"><span data-stu-id="5a260-104">ID</span></span>|<span data-ttu-id="5a260-105">3507</span><span class="sxs-lookup"><span data-stu-id="5a260-105">3507</span></span>|  
|<span data-ttu-id="5a260-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5a260-106">Keywords</span></span>|<span data-ttu-id="5a260-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="5a260-107">WFServices</span></span>|  
|<span data-ttu-id="5a260-108">级别</span><span class="sxs-lookup"><span data-stu-id="5a260-108">Level</span></span>|<span data-ttu-id="5a260-109">信息</span><span class="sxs-lookup"><span data-stu-id="5a260-109">Information</span></span>|  
|<span data-ttu-id="5a260-110">通道</span><span class="sxs-lookup"><span data-stu-id="5a260-110">Channel</span></span>|<span data-ttu-id="5a260-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="5a260-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5a260-112">描述</span><span class="sxs-lookup"><span data-stu-id="5a260-112">Description</span></span>  
 <span data-ttu-id="5a260-113">指示添加了服务终结点。</span><span class="sxs-lookup"><span data-stu-id="5a260-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5a260-114">消息</span><span class="sxs-lookup"><span data-stu-id="5a260-114">Message</span></span>  
 <span data-ttu-id="5a260-115">已为地址“%1”、绑定“%2”和协定“%3”添加了服务终结点。</span><span class="sxs-lookup"><span data-stu-id="5a260-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5a260-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a260-116">Details</span></span>  
  
|<span data-ttu-id="5a260-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5a260-117">Data Item Name</span></span>|<span data-ttu-id="5a260-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5a260-118">Data Item Type</span></span>|<span data-ttu-id="5a260-119">描述</span><span class="sxs-lookup"><span data-stu-id="5a260-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5a260-120">Address</span><span class="sxs-lookup"><span data-stu-id="5a260-120">Address</span></span>|<span data-ttu-id="5a260-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5a260-121">xs:string</span></span>|<span data-ttu-id="5a260-122">终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="5a260-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="5a260-123">绑定</span><span class="sxs-lookup"><span data-stu-id="5a260-123">Binding</span></span>|<span data-ttu-id="5a260-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5a260-124">xs:string</span></span>|<span data-ttu-id="5a260-125">终结点的绑定。</span><span class="sxs-lookup"><span data-stu-id="5a260-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="5a260-126">协定</span><span class="sxs-lookup"><span data-stu-id="5a260-126">Contract</span></span>|<span data-ttu-id="5a260-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5a260-127">xs:string</span></span>|<span data-ttu-id="5a260-128">终结点的协定。</span><span class="sxs-lookup"><span data-stu-id="5a260-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="5a260-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="5a260-129">AppDomain</span></span>|<span data-ttu-id="5a260-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5a260-130">xs:string</span></span>|<span data-ttu-id="5a260-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5a260-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
