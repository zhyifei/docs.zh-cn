---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756086"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="8a665-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="8a665-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="8a665-103">属性</span><span class="sxs-lookup"><span data-stu-id="8a665-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a665-104">Id</span><span class="sxs-lookup"><span data-stu-id="8a665-104">ID</span></span>|<span data-ttu-id="8a665-105">3502</span><span class="sxs-lookup"><span data-stu-id="8a665-105">3502</span></span>|  
|<span data-ttu-id="8a665-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8a665-106">Keywords</span></span>|<span data-ttu-id="8a665-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="8a665-107">WFServices</span></span>|  
|<span data-ttu-id="8a665-108">级别</span><span class="sxs-lookup"><span data-stu-id="8a665-108">Level</span></span>|<span data-ttu-id="8a665-109">信息</span><span class="sxs-lookup"><span data-stu-id="8a665-109">Information</span></span>|  
|<span data-ttu-id="8a665-110">通道</span><span class="sxs-lookup"><span data-stu-id="8a665-110">Channel</span></span>|<span data-ttu-id="8a665-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="8a665-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a665-112">描述</span><span class="sxs-lookup"><span data-stu-id="8a665-112">Description</span></span>  
 <span data-ttu-id="8a665-113">指示已从 WorkflowService 中推断出 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="8a665-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a665-114">消息</span><span class="sxs-lookup"><span data-stu-id="8a665-114">Message</span></span>  
 <span data-ttu-id="8a665-115">已从 WorkflowService 中推断出协定“%2”中含有 Name='%1' 的 OperationDescription。</span><span class="sxs-lookup"><span data-stu-id="8a665-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="8a665-116">IsOneWay=%3。</span><span class="sxs-lookup"><span data-stu-id="8a665-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a665-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="8a665-117">Details</span></span>  
  
|<span data-ttu-id="8a665-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8a665-118">Data Item Name</span></span>|<span data-ttu-id="8a665-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8a665-119">Data Item Type</span></span>|<span data-ttu-id="8a665-120">描述</span><span class="sxs-lookup"><span data-stu-id="8a665-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a665-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="8a665-121">OperationName</span></span>|<span data-ttu-id="8a665-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a665-122">xs:string</span></span>|<span data-ttu-id="8a665-123">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="8a665-123">The name of the operation.</span></span>|  
|<span data-ttu-id="8a665-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="8a665-124">ContractName</span></span>|<span data-ttu-id="8a665-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a665-125">xs:string</span></span>|<span data-ttu-id="8a665-126">协定的名称。</span><span class="sxs-lookup"><span data-stu-id="8a665-126">The name of the contract.</span></span>|  
|<span data-ttu-id="8a665-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="8a665-127">IsOneWay</span></span>|<span data-ttu-id="8a665-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a665-128">xs:string</span></span>|<span data-ttu-id="8a665-129">true 或 false 指示协定是否为单向。</span><span class="sxs-lookup"><span data-stu-id="8a665-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="8a665-130">应用程序域</span><span class="sxs-lookup"><span data-stu-id="8a665-130">AppDomain</span></span>|<span data-ttu-id="8a665-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a665-131">xs:string</span></span>|<span data-ttu-id="8a665-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8a665-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
