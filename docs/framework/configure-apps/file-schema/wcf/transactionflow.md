---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 2d1008a4308c9fda5d2291ce704d1f19205e996a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041254"
---
# <a name="transactionflow"></a><span data-ttu-id="25b08-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="25b08-101">\<transactionFlow></span></span>
<span data-ttu-id="25b08-102">指定自定义绑定的事务流支持。</span><span class="sxs-lookup"><span data-stu-id="25b08-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="25b08-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="25b08-103">\<system.serviceModel></span></span>  
<span data-ttu-id="25b08-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="25b08-104">\<bindings></span></span>  
<span data-ttu-id="25b08-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="25b08-105">\<customBinding></span></span>  
<span data-ttu-id="25b08-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="25b08-106">\<binding></span></span>  
<span data-ttu-id="25b08-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="25b08-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b08-108">语法</span><span class="sxs-lookup"><span data-stu-id="25b08-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25b08-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="25b08-109">Attributes and Elements</span></span>  
 <span data-ttu-id="25b08-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="25b08-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25b08-111">特性</span><span class="sxs-lookup"><span data-stu-id="25b08-111">Attributes</span></span>  
  
|<span data-ttu-id="25b08-112">特性</span><span class="sxs-lookup"><span data-stu-id="25b08-112">Attribute</span></span>|<span data-ttu-id="25b08-113">描述</span><span class="sxs-lookup"><span data-stu-id="25b08-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25b08-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="25b08-114">transactionProtocol</span></span>|<span data-ttu-id="25b08-115">指定要使用的事务处理协议。</span><span class="sxs-lookup"><span data-stu-id="25b08-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="25b08-116">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="25b08-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="25b08-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="25b08-117">-   OleTransactions</span></span><br /><span data-ttu-id="25b08-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="25b08-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="25b08-119">默认值为 OleTransactions。</span><span class="sxs-lookup"><span data-stu-id="25b08-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="25b08-120">此属性的类型为 <xref:System.ServiceModel.TransactionProtocol>。</span><span class="sxs-lookup"><span data-stu-id="25b08-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25b08-121">子元素</span><span class="sxs-lookup"><span data-stu-id="25b08-121">Child Elements</span></span>  
 <span data-ttu-id="25b08-122">无。</span><span class="sxs-lookup"><span data-stu-id="25b08-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25b08-123">父元素</span><span class="sxs-lookup"><span data-stu-id="25b08-123">Parent Elements</span></span>  
  
|<span data-ttu-id="25b08-124">元素</span><span class="sxs-lookup"><span data-stu-id="25b08-124">Element</span></span>|<span data-ttu-id="25b08-125">描述</span><span class="sxs-lookup"><span data-stu-id="25b08-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25b08-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="25b08-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="25b08-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="25b08-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25b08-128">备注</span><span class="sxs-lookup"><span data-stu-id="25b08-128">Remarks</span></span>  
 <span data-ttu-id="25b08-129">此元素允许你在终结点绑定设置中启用或禁用传入事务流，并允许指定传入事务所需的协议格式。</span><span class="sxs-lookup"><span data-stu-id="25b08-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="25b08-130">有关使用此配置元素的详细信息, 请参阅配置[配置](../../../wcf/feature-details/servicemodel-transaction-configuration.md)和[启用事务流](../../../wcf/feature-details/enabling-transaction-flow.md)。</span><span class="sxs-lookup"><span data-stu-id="25b08-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="25b08-131">使用 `OleTransactions` 协议在终结点之间对事务进行流处理时，如果目标终结点尝试使用任何 `OleTransactions` 之外的协议进行流处理，则可能丢失事务超时。</span><span class="sxs-lookup"><span data-stu-id="25b08-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="25b08-132">这可能导致 OleTransactions 跃点后面的所有下级节点的超时时间比预期延迟。</span><span class="sxs-lookup"><span data-stu-id="25b08-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b08-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="25b08-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="25b08-134">ServiceModel 事务配置</span><span class="sxs-lookup"><span data-stu-id="25b08-134">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="25b08-135">启用事务流</span><span class="sxs-lookup"><span data-stu-id="25b08-135">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="25b08-136">绑定</span><span class="sxs-lookup"><span data-stu-id="25b08-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="25b08-137">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="25b08-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="25b08-138">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="25b08-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="25b08-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="25b08-139">\<customBinding></span></span>](custombinding.md)
