---
title: "比较 COM+ 和 ServiceModel 中的事务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87e3df31060a9c71e0b2868aa34373bca221fa79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a><span data-ttu-id="b676a-102">比较 COM+ 和 ServiceModel 中的事务</span><span class="sxs-lookup"><span data-stu-id="b676a-102">Comparing Transactions in COM+ and ServiceModel</span></span>
<span data-ttu-id="b676a-103">本主题讨论如何使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 命名空间提供的 <xref:System.ServiceModel> 属性来模拟事务性 COM+ 服务的行为。</span><span class="sxs-lookup"><span data-stu-id="b676a-103">This topic discusses how to simulate the behavior of a transactional COM+ service using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
## <a name="emulating-com-using-servicemodel-attributes"></a><span data-ttu-id="b676a-104">使用 ServiceModel 属性模拟 COM+</span><span class="sxs-lookup"><span data-stu-id="b676a-104">Emulating COM+ Using ServiceModel Attributes</span></span>  
 <span data-ttu-id="b676a-105">下表比较用于创建 <xref:System.EnterpriseServices.TransactionOption> 事务的 `EnterpriseServices` 枚举，以及他们如何与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的 <xref:System.ServiceModel> 属性关联。</span><span class="sxs-lookup"><span data-stu-id="b676a-105">The following table compares the <xref:System.EnterpriseServices.TransactionOption> enumeration used to create an `EnterpriseServices` transaction and how they correlate to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
|<span data-ttu-id="b676a-106">COM+ 属性</span><span class="sxs-lookup"><span data-stu-id="b676a-106">COM+ attribute</span></span>|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b676a-107"> 属性</span><span class="sxs-lookup"><span data-stu-id="b676a-107"> attributes</span></span>|  
|---------------------|------------------------------------------------------------------------|  
|<span data-ttu-id="b676a-108">RequiresNew</span><span class="sxs-lookup"><span data-stu-id="b676a-108">RequiresNew</span></span>|<span data-ttu-id="b676a-109">将 <xref:System.ServiceModel.TransactionFlowAttribute> 设置为 <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>。</span><span class="sxs-lookup"><span data-stu-id="b676a-109"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span></span><br /><br /> <span data-ttu-id="b676a-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b676a-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="b676a-111">绑定元素中的 `TransactionFlow` 属性为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b676a-111">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="b676a-112">必需</span><span class="sxs-lookup"><span data-stu-id="b676a-112">Required</span></span>|<span data-ttu-id="b676a-113">将 <xref:System.ServiceModel.TransactionFlowAttribute> 设置为 <xref:System.ServiceModel.TransactionFlowOption.Allowed>。</span><span class="sxs-lookup"><span data-stu-id="b676a-113"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span></span><br /><br /> <span data-ttu-id="b676a-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b676a-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="b676a-115">绑定元素中的 `TransactionFlow` 属性为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b676a-115">The `TransactionFlow` attribute in the binding element is `true`.</span></span>|  
|<span data-ttu-id="b676a-116">支持</span><span class="sxs-lookup"><span data-stu-id="b676a-116">Supported</span></span>|<span data-ttu-id="b676a-117">没有直接等效项。</span><span class="sxs-lookup"><span data-stu-id="b676a-117">There is no direct equivalent.</span></span> <span data-ttu-id="b676a-118">通常，您应采用为 `Required` 指定的行为。</span><span class="sxs-lookup"><span data-stu-id="b676a-118">In general, you should adopt the behavior specified for `Required` instead.</span></span>|  
|<span data-ttu-id="b676a-119">NotSupported</span><span class="sxs-lookup"><span data-stu-id="b676a-119">NotSupported</span></span>|<span data-ttu-id="b676a-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b676a-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `false`.</span></span><br /><br /> <span data-ttu-id="b676a-121">绑定元素中的 `TransactionFlow` 属性为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b676a-121">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="b676a-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="b676a-122">Disabled</span></span>|<span data-ttu-id="b676a-123">没有直接等效项。</span><span class="sxs-lookup"><span data-stu-id="b676a-123">There is no direct equivalent.</span></span> <span data-ttu-id="b676a-124">通常，您应采用为 `NotSupported` 指定的行为。</span><span class="sxs-lookup"><span data-stu-id="b676a-124">In general, you should adopt the behavior specified for `NotSupported` instead.</span></span>|
