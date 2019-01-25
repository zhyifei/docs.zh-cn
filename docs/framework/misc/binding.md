---
title: '&lt;binding&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
ms.openlocfilehash: fb4fafda31205e2ce5efd01ab265fcacfa70bdf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539189"
---
# <a name="ltbindinggt"></a><span data-ttu-id="3688f-102">&lt;binding&gt;</span><span class="sxs-lookup"><span data-stu-id="3688f-102">&lt;binding&gt;</span></span>
<span data-ttu-id="3688f-103">可以使用 `binding` 元素来配置 Windows Communication Foundation (WCF) 提供的不同类型的预定义绑定。</span><span class="sxs-lookup"><span data-stu-id="3688f-103">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="3688f-104">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="3688f-104">System-Provided Binding</span></span>  
 <span data-ttu-id="3688f-105">系统提供的绑定可以消除 WCF 消息堆栈的复杂性。</span><span class="sxs-lookup"><span data-stu-id="3688f-105">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="3688f-106">使用系统提供的绑定的应用程序不需要对堆栈的完全控制权限。</span><span class="sxs-lookup"><span data-stu-id="3688f-106">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="3688f-107">在每个系统提供的绑定上公开的属性最适合绑定所针对的使用方案。</span><span class="sxs-lookup"><span data-stu-id="3688f-107">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="3688f-108">每个系统提供的绑定的配置节可以定义用于配置此绑定的一些配置。</span><span class="sxs-lookup"><span data-stu-id="3688f-108">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="3688f-109">每个配置均由唯一的名称进行标识。</span><span class="sxs-lookup"><span data-stu-id="3688f-109">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="3688f-110">无法向系统提供的绑定添加元素或属性。</span><span class="sxs-lookup"><span data-stu-id="3688f-110">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="3688f-111">为此，应该按照本主题的“自定义绑定”节中的描述来实现自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="3688f-111">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="3688f-112">可以定义一个自定义绑定，该自定义绑定将完全模仿系统提供的绑定，并添加用户应用程序希望获得其控制权限的一些设置。</span><span class="sxs-lookup"><span data-stu-id="3688f-112">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="3688f-113">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="3688f-113">Custom Binding</span></span>  
 <span data-ttu-id="3688f-114">自定义绑定提供了对 WCF 消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="3688f-114">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="3688f-115">单个绑定按照堆栈元素在堆栈上出现的顺序来指定它们的配置元素，从而定义消息堆栈。</span><span class="sxs-lookup"><span data-stu-id="3688f-115">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="3688f-116">每个元素都定义和配置了该堆栈的一个元素。</span><span class="sxs-lookup"><span data-stu-id="3688f-116">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="3688f-117">在每个自定义绑定中，必须有且只能有一个 `transport` 元素。</span><span class="sxs-lookup"><span data-stu-id="3688f-117">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="3688f-118">如果没有该元素，消息堆栈将是不完整的。</span><span class="sxs-lookup"><span data-stu-id="3688f-118">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="3688f-119">元素在堆栈中出现的顺序非常重要，因为在将操作应用于消息时会采用该顺序。</span><span class="sxs-lookup"><span data-stu-id="3688f-119">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="3688f-120">建议的堆栈元素顺序如下：</span><span class="sxs-lookup"><span data-stu-id="3688f-120">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="3688f-121">事务（可选）</span><span class="sxs-lookup"><span data-stu-id="3688f-121">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="3688f-122">可靠消息（可选）</span><span class="sxs-lookup"><span data-stu-id="3688f-122">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="3688f-123">安全（可选）</span><span class="sxs-lookup"><span data-stu-id="3688f-123">Security (optional)</span></span>  
  
4.  <span data-ttu-id="3688f-124">编码器</span><span class="sxs-lookup"><span data-stu-id="3688f-124">Encoder</span></span>  
  
5.  <span data-ttu-id="3688f-125">传输</span><span class="sxs-lookup"><span data-stu-id="3688f-125">Transport</span></span>  
  
 <span data-ttu-id="3688f-126">自定义绑定由其 `name` 特性来标识。</span><span class="sxs-lookup"><span data-stu-id="3688f-126">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3688f-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="3688f-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- [<span data-ttu-id="3688f-128">绑定</span><span class="sxs-lookup"><span data-stu-id="3688f-128">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="3688f-129">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="3688f-129">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3688f-130">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3688f-130">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
