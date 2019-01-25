---
title: '&lt;transactionFlow&gt;'
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: d8597a71a9b7afadba7565290085f491052e04d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622112"
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="d2fa7-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="d2fa7-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="d2fa7-103">指定自定义绑定的事务流支持。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="d2fa7-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d2fa7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d2fa7-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d2fa7-105">\<bindings></span></span>  
<span data-ttu-id="d2fa7-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d2fa7-106">\<customBinding></span></span>  
<span data-ttu-id="d2fa7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="d2fa7-107">\<binding></span></span>  
<span data-ttu-id="d2fa7-108">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="d2fa7-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2fa7-109">语法</span><span class="sxs-lookup"><span data-stu-id="d2fa7-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2fa7-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2fa7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2fa7-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2fa7-112">特性</span><span class="sxs-lookup"><span data-stu-id="d2fa7-112">Attributes</span></span>  
  
|<span data-ttu-id="d2fa7-113">特性</span><span class="sxs-lookup"><span data-stu-id="d2fa7-113">Attribute</span></span>|<span data-ttu-id="d2fa7-114">描述</span><span class="sxs-lookup"><span data-stu-id="d2fa7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2fa7-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="d2fa7-115">transactionProtocol</span></span>|<span data-ttu-id="d2fa7-116">指定要使用的事务处理协议。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="d2fa7-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="d2fa7-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d2fa7-118">-   OleTransactions</span><span class="sxs-lookup"><span data-stu-id="d2fa7-118">-   OleTransactions</span></span><br /><span data-ttu-id="d2fa7-119">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="d2fa7-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="d2fa7-120">默认值为 OleTransactions。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="d2fa7-121">此属性的类型为 <xref:System.ServiceModel.TransactionProtocol>。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2fa7-122">子元素</span><span class="sxs-lookup"><span data-stu-id="d2fa7-122">Child Elements</span></span>  
 <span data-ttu-id="d2fa7-123">无。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2fa7-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d2fa7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d2fa7-125">元素</span><span class="sxs-lookup"><span data-stu-id="d2fa7-125">Element</span></span>|<span data-ttu-id="d2fa7-126">描述</span><span class="sxs-lookup"><span data-stu-id="d2fa7-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2fa7-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="d2fa7-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d2fa7-128">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2fa7-129">备注</span><span class="sxs-lookup"><span data-stu-id="d2fa7-129">Remarks</span></span>  
 <span data-ttu-id="d2fa7-130">此元素允许你在终结点绑定设置中启用或禁用传入事务流，并允许指定传入事务所需的协议格式。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="d2fa7-131">使用此配置元素的详细信息，请参阅[ServiceModel 事务配置](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)并[启用事务流](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d2fa7-132">使用 `OleTransactions` 协议在终结点之间对事务进行流处理时，如果目标终结点尝试使用任何 `OleTransactions` 之外的协议进行流处理，则可能丢失事务超时。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="d2fa7-133">这可能导致 OleTransactions 跃点后面的所有下级节点的超时时间比预期延迟。</span><span class="sxs-lookup"><span data-stu-id="d2fa7-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2fa7-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2fa7-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d2fa7-135">ServiceModel 事务配置</span><span class="sxs-lookup"><span data-stu-id="d2fa7-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="d2fa7-136">启用事务流</span><span class="sxs-lookup"><span data-stu-id="d2fa7-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="d2fa7-137">绑定</span><span class="sxs-lookup"><span data-stu-id="d2fa7-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d2fa7-138">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="d2fa7-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d2fa7-139">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="d2fa7-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d2fa7-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d2fa7-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
