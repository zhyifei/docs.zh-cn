---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: ef3d92e07aaf4d4ba9d90e381017db104f2cc8fe
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356580"
---
# <a name="transactionflow"></a><span data-ttu-id="72653-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="72653-101">\<transactionFlow></span></span>
<span data-ttu-id="72653-102">指定自定义绑定的事务流支持。</span><span class="sxs-lookup"><span data-stu-id="72653-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="72653-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="72653-103">\<system.serviceModel></span></span>  
<span data-ttu-id="72653-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="72653-104">\<bindings></span></span>  
<span data-ttu-id="72653-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="72653-105">\<customBinding></span></span>  
<span data-ttu-id="72653-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="72653-106">\<binding></span></span>  
<span data-ttu-id="72653-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="72653-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72653-108">语法</span><span class="sxs-lookup"><span data-stu-id="72653-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72653-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="72653-109">Attributes and Elements</span></span>  
 <span data-ttu-id="72653-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="72653-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72653-111">特性</span><span class="sxs-lookup"><span data-stu-id="72653-111">Attributes</span></span>  
  
|<span data-ttu-id="72653-112">特性</span><span class="sxs-lookup"><span data-stu-id="72653-112">Attribute</span></span>|<span data-ttu-id="72653-113">描述</span><span class="sxs-lookup"><span data-stu-id="72653-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72653-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="72653-114">transactionProtocol</span></span>|<span data-ttu-id="72653-115">指定要使用的事务处理协议。</span><span class="sxs-lookup"><span data-stu-id="72653-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="72653-116">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="72653-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="72653-117">-   OleTransactions</span><span class="sxs-lookup"><span data-stu-id="72653-117">-   OleTransactions</span></span><br /><span data-ttu-id="72653-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="72653-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="72653-119">默认值为 OleTransactions。</span><span class="sxs-lookup"><span data-stu-id="72653-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="72653-120">此属性的类型为 <xref:System.ServiceModel.TransactionProtocol>。</span><span class="sxs-lookup"><span data-stu-id="72653-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72653-121">子元素</span><span class="sxs-lookup"><span data-stu-id="72653-121">Child Elements</span></span>  
 <span data-ttu-id="72653-122">无。</span><span class="sxs-lookup"><span data-stu-id="72653-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72653-123">父元素</span><span class="sxs-lookup"><span data-stu-id="72653-123">Parent Elements</span></span>  
  
|<span data-ttu-id="72653-124">元素</span><span class="sxs-lookup"><span data-stu-id="72653-124">Element</span></span>|<span data-ttu-id="72653-125">描述</span><span class="sxs-lookup"><span data-stu-id="72653-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72653-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="72653-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="72653-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="72653-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72653-128">备注</span><span class="sxs-lookup"><span data-stu-id="72653-128">Remarks</span></span>  
 <span data-ttu-id="72653-129">此元素允许你在终结点绑定设置中启用或禁用传入事务流，并允许指定传入事务所需的协议格式。</span><span class="sxs-lookup"><span data-stu-id="72653-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="72653-130">使用此配置元素的详细信息，请参阅[ServiceModel 事务配置](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)并[启用事务流](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)。</span><span class="sxs-lookup"><span data-stu-id="72653-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="72653-131">使用 `OleTransactions` 协议在终结点之间对事务进行流处理时，如果目标终结点尝试使用任何 `OleTransactions` 之外的协议进行流处理，则可能丢失事务超时。</span><span class="sxs-lookup"><span data-stu-id="72653-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="72653-132">这可能导致 OleTransactions 跃点后面的所有下级节点的超时时间比预期延迟。</span><span class="sxs-lookup"><span data-stu-id="72653-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72653-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="72653-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="72653-134">ServiceModel 事务配置</span><span class="sxs-lookup"><span data-stu-id="72653-134">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="72653-135">启用事务流</span><span class="sxs-lookup"><span data-stu-id="72653-135">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="72653-136">绑定</span><span class="sxs-lookup"><span data-stu-id="72653-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="72653-137">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="72653-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="72653-138">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="72653-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="72653-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="72653-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
