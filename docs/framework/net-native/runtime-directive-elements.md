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
ms.openlocfilehash: 3143c6b78749f3339e7e7195b551b5a5c31fad12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="09328-102">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="09328-102">Runtime Directive Elements</span></span>
<span data-ttu-id="09328-103">运行时指令 (rd.xml) 文件格式支持以下运行时指令元素。</span><span class="sxs-lookup"><span data-stu-id="09328-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="09328-104">请参阅[运行时指令 (rd.xml) 配置文件参考](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)了解分层表示形式。</span><span class="sxs-lookup"><span data-stu-id="09328-104">See [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="09328-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="09328-105">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 <span data-ttu-id="09328-106">将运行时反射策略应用到该应用使用的所有类型，作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="09328-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="09328-107">这是 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-107">This is a child of the [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="09328-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="09328-108">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 <span data-ttu-id="09328-109">将运行时策略应用到程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="09328-109">Applies runnntime policy to all the types in an assembly.</span></span> <span data-ttu-id="09328-110">这是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 和 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-110">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09328-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="09328-111">\<AttributeImplies></span></span>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 <span data-ttu-id="09328-112">如果它包含的 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 指令是一个属性，则将运行时策略应用到应用了该属性的代码元素。</span><span class="sxs-lookup"><span data-stu-id="09328-112">If its containing [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="09328-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="09328-113">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 <span data-ttu-id="09328-114">根元素位于 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 的每个运行时指令文件中。</span><span class="sxs-lookup"><span data-stu-id="09328-114">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="09328-115">它的子元素是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 和 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)。</span><span class="sxs-lookup"><span data-stu-id="09328-115">Its child elements are [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="09328-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="09328-116">\<Event></span></span>](../../../docs/framework/net-native/event-element-net-native.md)  
 <span data-ttu-id="09328-117">将运行时策略应用到一个事件。</span><span class="sxs-lookup"><span data-stu-id="09328-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="09328-118">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-118">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09328-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="09328-119">\<Field></span></span>](../../../docs/framework/net-native/field-element-net-native.md)  
 <span data-ttu-id="09328-120">将运行时策略应用到一个字段。</span><span class="sxs-lookup"><span data-stu-id="09328-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="09328-121">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-121">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09328-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="09328-122">\<GenericParameter></span></span>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 <span data-ttu-id="09328-123">将运行时策略应用到一个泛型类型或方法的参数类型。</span><span class="sxs-lookup"><span data-stu-id="09328-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="09328-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="09328-124">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 <span data-ttu-id="09328-125">如果该策略已应用到该包含类型或方法，将该运行时策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="09328-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="09328-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="09328-126">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)  
 <span data-ttu-id="09328-127">将运行时策略应用到程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="09328-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="09328-128">这是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 和 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-128">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09328-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="09328-129">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 <span data-ttu-id="09328-130">将运行时策略应用到一个方法。</span><span class="sxs-lookup"><span data-stu-id="09328-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="09328-131">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-131">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09328-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="09328-132">\<MethodInstantiation></span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 <span data-ttu-id="09328-133">将运行时策略应用到一个构造泛型方法。</span><span class="sxs-lookup"><span data-stu-id="09328-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="09328-134">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-134">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09328-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="09328-135">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 <span data-ttu-id="09328-136">将运行时策略应用到命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="09328-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="09328-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="09328-137">\<Parameter></span></span>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 <span data-ttu-id="09328-138">将运行时策略应用到传递到方法的自变量类型。</span><span class="sxs-lookup"><span data-stu-id="09328-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="09328-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="09328-139">\<Property></span></span>](../../../docs/framework/net-native/property-element-net-native.md)  
 <span data-ttu-id="09328-140">将运行时策略应用到一个属性。</span><span class="sxs-lookup"><span data-stu-id="09328-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="09328-141">这是 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 和 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="09328-141">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="09328-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="09328-142">\<Subtypes></span></span>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 <span data-ttu-id="09328-143">将运行时策略应用到从包含类型继承的所有类。</span><span class="sxs-lookup"><span data-stu-id="09328-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="09328-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="09328-144">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 <span data-ttu-id="09328-145">将运行时策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="09328-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="09328-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="09328-146">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 <span data-ttu-id="09328-147">将运行时策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="09328-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="09328-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="09328-148">\<TypeParameter></span></span>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 <span data-ttu-id="09328-149">将运行时策略应用到以传递到方法为代表的 <xref:System.Type> 参数类型。</span><span class="sxs-lookup"><span data-stu-id="09328-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09328-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09328-150">See Also</span></span>  
 [<span data-ttu-id="09328-151">rd.xml 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="09328-151">rd.xml Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
