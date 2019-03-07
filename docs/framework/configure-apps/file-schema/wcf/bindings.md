---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: 7cafd8c1ba96a4fa1014f3570413b4bb83f69766
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474717"
---
# <a name="bindings"></a><span data-ttu-id="fa31d-101">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fa31d-101">\<bindings></span></span>

<span data-ttu-id="fa31d-102">可以使用`bindings`元素来配置 Windows Communication Foundation (WCF) 的标准和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="fa31d-102">You can use the `bindings` element to configure a collection of standard and custom bindings for Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="fa31d-103">每一项都是一个可由其唯一 `binding` 进行标识的 `name` 元素。</span><span class="sxs-lookup"><span data-stu-id="fa31d-103">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="fa31d-104">服务通过用 `name` 与绑定进行链接来使用绑定。</span><span class="sxs-lookup"><span data-stu-id="fa31d-104">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="fa31d-105">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="fa31d-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="fa31d-106">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="fa31d-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="system-provided-bindings"></a><span data-ttu-id="fa31d-107">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="fa31d-107">System-provided bindings</span></span>
 
 <span data-ttu-id="fa31d-108">系统提供的绑定可以消除 WCF 消息堆栈的复杂性。</span><span class="sxs-lookup"><span data-stu-id="fa31d-108">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="fa31d-109">使用系统提供的绑定的应用程序不需要对堆栈的完全控制权限。</span><span class="sxs-lookup"><span data-stu-id="fa31d-109">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="fa31d-110">在每个系统提供的绑定上公开的属性最适合绑定所针对的使用方案。</span><span class="sxs-lookup"><span data-stu-id="fa31d-110">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="fa31d-111">每个系统提供的绑定的配置节可以定义用于配置此绑定的一些配置。</span><span class="sxs-lookup"><span data-stu-id="fa31d-111">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="fa31d-112">每个配置均由唯一的名称进行标识。</span><span class="sxs-lookup"><span data-stu-id="fa31d-112">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="fa31d-113">它不能向系统提供的绑定添加元素或属性。</span><span class="sxs-lookup"><span data-stu-id="fa31d-113">It isn't possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="fa31d-114">若要执行此操作，则应实现自定义绑定中所述[自定义绑定](#custom-bindings)部分。</span><span class="sxs-lookup"><span data-stu-id="fa31d-114">To do so, you should implement a custom binding as described in the [Custom bindings](#custom-bindings) section.</span></span> <span data-ttu-id="fa31d-115">它是可以定义自定义绑定，模仿系统提供的绑定完全并添加用户应用程序想要控制的一些设置。</span><span class="sxs-lookup"><span data-stu-id="fa31d-115">It's possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
 <span data-ttu-id="fa31d-116">有关系统提供的绑定的列表，请参阅[System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="fa31d-116">For a list of system-provided bindings, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="custom-bindings"></a><span data-ttu-id="fa31d-117">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="fa31d-117">Custom bindings</span></span>

 <span data-ttu-id="fa31d-118">自定义绑定提供了对 WCF 消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="fa31d-118">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="fa31d-119">单个绑定按照堆栈元素在堆栈上出现的顺序来指定它们的配置元素，从而定义消息堆栈。</span><span class="sxs-lookup"><span data-stu-id="fa31d-119">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="fa31d-120">每个元素定义和配置堆栈的一个元素。</span><span class="sxs-lookup"><span data-stu-id="fa31d-120">Each element defines and configures one element of the stack.</span></span> <span data-ttu-id="fa31d-121">在每个自定义绑定中，必须有且只能有一个 `transport` 元素。</span><span class="sxs-lookup"><span data-stu-id="fa31d-121">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="fa31d-122">如果没有该元素，消息堆栈将是不完整的。</span><span class="sxs-lookup"><span data-stu-id="fa31d-122">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="fa31d-123">元素在堆栈中出现的顺序非常重要，因为在将操作应用于消息时会采用该顺序。</span><span class="sxs-lookup"><span data-stu-id="fa31d-123">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="fa31d-124">所需的堆栈元素顺序如下：</span><span class="sxs-lookup"><span data-stu-id="fa31d-124">The required order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="fa31d-125">事务（可选）</span><span class="sxs-lookup"><span data-stu-id="fa31d-125">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="fa31d-126">可靠消息传送 （可选）</span><span class="sxs-lookup"><span data-stu-id="fa31d-126">Reliable messaging (optional)</span></span>  
  
3.  <span data-ttu-id="fa31d-127">安全（可选）</span><span class="sxs-lookup"><span data-stu-id="fa31d-127">Security (optional)</span></span>  
  
4.  <span data-ttu-id="fa31d-128">编码器</span><span class="sxs-lookup"><span data-stu-id="fa31d-128">Encoder</span></span>  
  
5.  <span data-ttu-id="fa31d-129">传输</span><span class="sxs-lookup"><span data-stu-id="fa31d-129">Transport</span></span>  
  
 <span data-ttu-id="fa31d-130">自定义绑定由其 `name` 特性来标识。</span><span class="sxs-lookup"><span data-stu-id="fa31d-130">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="fa31d-131">自定义绑定的详细信息，请参阅[自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="fa31d-131">For more information on custom bindings, see [Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa31d-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa31d-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>  
- [<span data-ttu-id="fa31d-133">绑定</span><span class="sxs-lookup"><span data-stu-id="fa31d-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
- [<span data-ttu-id="fa31d-134">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="fa31d-134">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
- [<span data-ttu-id="fa31d-135">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fa31d-135">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
- [<span data-ttu-id="fa31d-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa31d-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
