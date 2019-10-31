---
title: 运行时指令元素
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128174"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="4d552-102">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="4d552-102">Runtime Directive Elements</span></span>
<span data-ttu-id="4d552-103">运行时指令 (rd.xml) 文件格式支持以下运行时指令元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="4d552-104">请参阅[运行时指令 (rd.xml) 配置文件参考](runtime-directives-rd-xml-configuration-file-reference.md)了解分层表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d552-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="4d552-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="4d552-105">\<Application></span></span>](application-element-net-native.md)  
 <span data-ttu-id="4d552-106">将运行时反射策略应用到该应用使用的所有类型，作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="4d552-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="4d552-107">这是 [\<Directives>](directives-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="4d552-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="4d552-108">\<Assembly></span></span>](assembly-element-net-native.md)  
 <span data-ttu-id="4d552-109">将运行时策略应用到程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="4d552-110">这是 [\<Application>](application-element-net-native.md) 和 [\<Library>](library-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-110">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="4d552-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="4d552-111">\<AttributeImplies></span></span>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="4d552-112">如果它包含的 [\<Type>](type-element-net-native.md) 指令是一个属性，则将运行时策略应用到应用了该属性的代码元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-112">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="4d552-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="4d552-113">\<Directives></span></span>](directives-element-net-native.md)  
 <span data-ttu-id="4d552-114">.NET Native 的每个运行时指令文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-114">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="4d552-115">它的子元素是 [\<Application>](application-element-net-native.md) 和 [\<Library>](library-element-net-native.md)。</span><span class="sxs-lookup"><span data-stu-id="4d552-115">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="4d552-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="4d552-116">\<Event></span></span>](event-element-net-native.md)  
 <span data-ttu-id="4d552-117">将运行时策略应用到一个事件。</span><span class="sxs-lookup"><span data-stu-id="4d552-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="4d552-118">这是 [\<Type>](type-element-net-native.md) 和 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-118">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="4d552-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="4d552-119">\<Field></span></span>](field-element-net-native.md)  
 <span data-ttu-id="4d552-120">将运行时策略应用到一个字段。</span><span class="sxs-lookup"><span data-stu-id="4d552-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="4d552-121">这是 [\<Type>](type-element-net-native.md) 和 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="4d552-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="4d552-122">\<GenericParameter></span></span>](genericparameter-element-net-native.md)  
 <span data-ttu-id="4d552-123">将运行时策略应用到一个泛型类型或方法的参数类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="4d552-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="4d552-124">\<ImpliesType></span></span>](impliestype-element-net-native.md)  
 <span data-ttu-id="4d552-125">如果该策略已应用到该包含类型或方法，将该运行时策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="4d552-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="4d552-126">\<Library></span></span>](library-element-net-native.md)  
 <span data-ttu-id="4d552-127">将运行时策略应用到程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="4d552-128">这是 [\<Application>](application-element-net-native.md) 和 [\<Library>](library-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-128">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="4d552-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="4d552-129">\<Method></span></span>](method-element-net-native.md)  
 <span data-ttu-id="4d552-130">将运行时策略应用到一个方法。</span><span class="sxs-lookup"><span data-stu-id="4d552-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="4d552-131">这是 [\<Type>](type-element-net-native.md) 和 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-131">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="4d552-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="4d552-132">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="4d552-133">将运行时策略应用到一个构造泛型方法。</span><span class="sxs-lookup"><span data-stu-id="4d552-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="4d552-134">这是 [\<Type>](type-element-net-native.md) 和 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-134">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="4d552-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="4d552-135">\<Namespace></span></span>](namespace-element-net-native.md)  
 <span data-ttu-id="4d552-136">将运行时策略应用到命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="4d552-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="4d552-137">\<Parameter></span></span>](parameter-element-net-native.md)  
 <span data-ttu-id="4d552-138">将运行时策略应用到传递到方法的参数类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="4d552-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="4d552-139">\<Property></span></span>](property-element-net-native.md)  
 <span data-ttu-id="4d552-140">将运行时策略应用到一个属性。</span><span class="sxs-lookup"><span data-stu-id="4d552-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="4d552-141">这是 [\<Type>](type-element-net-native.md) 和 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d552-141">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="4d552-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="4d552-142">\<Subtypes></span></span>](subtypes-element-net-native.md)  
 <span data-ttu-id="4d552-143">将运行时策略应用到从包含类型继承的所有类。</span><span class="sxs-lookup"><span data-stu-id="4d552-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="4d552-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="4d552-144">\<Type></span></span>](type-element-net-native.md)  
 <span data-ttu-id="4d552-145">将运行时策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="4d552-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="4d552-146">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="4d552-147">将运行时策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="4d552-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="4d552-148">\<TypeParameter></span></span>](typeparameter-element-net-native.md)  
 <span data-ttu-id="4d552-149">将运行时策略应用到以传递到方法为代表的 <xref:System.Type> 自变量类型。</span><span class="sxs-lookup"><span data-stu-id="4d552-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d552-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d552-150">See also</span></span>

- [<span data-ttu-id="4d552-151">rd.xml 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="4d552-151">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
