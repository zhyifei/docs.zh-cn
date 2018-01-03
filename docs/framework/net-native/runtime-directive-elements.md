---
title: "运行时指令元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2566c5ebe8c94610c8f7e258da7c77adb86a49f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="9d847-102">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="9d847-102">Runtime Directive Elements</span></span>
<span data-ttu-id="9d847-103">运行时指令 (rd.xml) 文件格式支持以下运行时指令元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="9d847-104">请参阅[运行时指令 (rd.xml) 配置文件参考](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)了解分层表示形式。</span><span class="sxs-lookup"><span data-stu-id="9d847-104">See [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="9d847-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="9d847-105">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 <span data-ttu-id="9d847-106">将运行时反射策略应用到该应用使用的所有类型，作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="9d847-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="9d847-107">这是 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-107">This is a child of the [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="9d847-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="9d847-108">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 <span data-ttu-id="9d847-109">将运行时策略应用到程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-109">Applies runnntime policy to all the types in an assembly.</span></span> <span data-ttu-id="9d847-110">这是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 和 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-110">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="9d847-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="9d847-111">\<AttributeImplies></span></span>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 <span data-ttu-id="9d847-112">如果它包含的 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 指令是一个属性，则将运行时策略应用到应用了该属性的代码元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-112">If its containing [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="9d847-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="9d847-113">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 <span data-ttu-id="9d847-114">根元素位于 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 的每个运行时指令文件中。</span><span class="sxs-lookup"><span data-stu-id="9d847-114">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="9d847-115">它的子元素是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 和 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)。</span><span class="sxs-lookup"><span data-stu-id="9d847-115">Its child elements are [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="9d847-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="9d847-116">\<Event></span></span>](../../../docs/framework/net-native/event-element-net-native.md)  
 <span data-ttu-id="9d847-117">将运行时策略应用到一个事件。</span><span class="sxs-lookup"><span data-stu-id="9d847-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="9d847-118">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-118">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="9d847-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="9d847-119">\<Field></span></span>](../../../docs/framework/net-native/field-element-net-native.md)  
 <span data-ttu-id="9d847-120">将运行时策略应用到一个字段。</span><span class="sxs-lookup"><span data-stu-id="9d847-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="9d847-121">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-121">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="9d847-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="9d847-122">\<GenericParameter></span></span>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 <span data-ttu-id="9d847-123">将运行时策略应用到一个泛型类型或方法的参数类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="9d847-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="9d847-124">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 <span data-ttu-id="9d847-125">如果该策略已应用到该包含类型或方法，将该运行时策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="9d847-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="9d847-126">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)  
 <span data-ttu-id="9d847-127">将运行时策略应用到程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="9d847-128">这是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 和 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-128">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="9d847-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="9d847-129">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 <span data-ttu-id="9d847-130">将运行时策略应用到一个方法。</span><span class="sxs-lookup"><span data-stu-id="9d847-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="9d847-131">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-131">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="9d847-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="9d847-132">\<MethodInstantiation></span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 <span data-ttu-id="9d847-133">将运行时策略应用到一个构造泛型方法。</span><span class="sxs-lookup"><span data-stu-id="9d847-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="9d847-134">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-134">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="9d847-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="9d847-135">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 <span data-ttu-id="9d847-136">将运行时策略应用到命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="9d847-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="9d847-137">\<Parameter></span></span>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 <span data-ttu-id="9d847-138">将运行时策略应用到传递到方法的自变量类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="9d847-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="9d847-139">\<Property></span></span>](../../../docs/framework/net-native/property-element-net-native.md)  
 <span data-ttu-id="9d847-140">将运行时策略应用到一个属性。</span><span class="sxs-lookup"><span data-stu-id="9d847-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="9d847-141">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d847-141">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="9d847-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="9d847-142">\<Subtypes></span></span>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 <span data-ttu-id="9d847-143">将运行时策略应用到从包含类型继承的所有类。</span><span class="sxs-lookup"><span data-stu-id="9d847-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="9d847-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="9d847-144">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 <span data-ttu-id="9d847-145">将运行时策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="9d847-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="9d847-146">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 <span data-ttu-id="9d847-147">将运行时策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="9d847-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="9d847-148">\<TypeParameter></span></span>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 <span data-ttu-id="9d847-149">将运行时策略应用到以传递到方法为代表的 <xref:System.Type> 参数类型。</span><span class="sxs-lookup"><span data-stu-id="9d847-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d847-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d847-150">See Also</span></span>  
 [<span data-ttu-id="9d847-151">rd.xml 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="9d847-151">rd.xml Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
