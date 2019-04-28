---
title: 3501 - InferredContractDescription
ms.date: 03/30/2017
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
ms.openlocfilehash: 47a5d98f4510e8c6092e8533a98366141d4b24db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755891"
---
# <a name="3501---inferredcontractdescription"></a><span data-ttu-id="a077b-102">3501 - InferredContractDescription</span><span class="sxs-lookup"><span data-stu-id="a077b-102">3501 - InferredContractDescription</span></span>
## <a name="properties"></a><span data-ttu-id="a077b-103">属性</span><span class="sxs-lookup"><span data-stu-id="a077b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a077b-104">Id</span><span class="sxs-lookup"><span data-stu-id="a077b-104">ID</span></span>|<span data-ttu-id="a077b-105">3501</span><span class="sxs-lookup"><span data-stu-id="a077b-105">3501</span></span>|  
|<span data-ttu-id="a077b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="a077b-106">Keywords</span></span>|<span data-ttu-id="a077b-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="a077b-107">WFServices</span></span>|  
|<span data-ttu-id="a077b-108">级别</span><span class="sxs-lookup"><span data-stu-id="a077b-108">Level</span></span>|<span data-ttu-id="a077b-109">信息</span><span class="sxs-lookup"><span data-stu-id="a077b-109">Information</span></span>|  
|<span data-ttu-id="a077b-110">通道</span><span class="sxs-lookup"><span data-stu-id="a077b-110">Channel</span></span>|<span data-ttu-id="a077b-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="a077b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a077b-112">描述</span><span class="sxs-lookup"><span data-stu-id="a077b-112">Description</span></span>  
 <span data-ttu-id="a077b-113">指示已从 WorkflowService 中推断出 ContractDescription。</span><span class="sxs-lookup"><span data-stu-id="a077b-113">Indicates a ContractDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a077b-114">消息</span><span class="sxs-lookup"><span data-stu-id="a077b-114">Message</span></span>  
 <span data-ttu-id="a077b-115">已从 WorkflowService 中推断出含有 Name 为“%1”和 Namespace 为“%2”的 ContractDescription。</span><span class="sxs-lookup"><span data-stu-id="a077b-115">ContractDescription with Name='%1' and Namespace='%2' has been inferred from WorkflowService.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a077b-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="a077b-116">Details</span></span>  
  
|<span data-ttu-id="a077b-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="a077b-117">Data Item Name</span></span>|<span data-ttu-id="a077b-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="a077b-118">Data Item Type</span></span>|<span data-ttu-id="a077b-119">描述</span><span class="sxs-lookup"><span data-stu-id="a077b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a077b-120">名称</span><span class="sxs-lookup"><span data-stu-id="a077b-120">Name</span></span>|<span data-ttu-id="a077b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a077b-121">xs:string</span></span>|<span data-ttu-id="a077b-122">ContractDescription 的名称。</span><span class="sxs-lookup"><span data-stu-id="a077b-122">The name of the ContractDescription.</span></span>|  
|<span data-ttu-id="a077b-123">命名空间</span><span class="sxs-lookup"><span data-stu-id="a077b-123">Namespace</span></span>|<span data-ttu-id="a077b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a077b-124">xs:string</span></span>|<span data-ttu-id="a077b-125">ContractDescription 的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a077b-125">The namespace of the ContractDescription.</span></span>|  
|<span data-ttu-id="a077b-126">应用程序域</span><span class="sxs-lookup"><span data-stu-id="a077b-126">AppDomain</span></span>|<span data-ttu-id="a077b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a077b-127">xs:string</span></span>|<span data-ttu-id="a077b-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a077b-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
