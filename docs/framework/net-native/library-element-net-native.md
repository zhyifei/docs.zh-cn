---
title: "&lt;Library&gt; 元素 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd2663bbd5ca93341455b7bd036469d25d91f4a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltlibrarygt-element-net-native"></a><span data-ttu-id="634f1-102">&lt;Library&gt; 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="634f1-102">&lt;Library&gt; Element (.NET Native)</span></span>
<span data-ttu-id="634f1-103">定义包含元数据在运行时间可以用于反射的类型和类型成员的程序集。</span><span class="sxs-lookup"><span data-stu-id="634f1-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="634f1-104">\<Directives> 元素</span><span class="sxs-lookup"><span data-stu-id="634f1-104">\<Directives> Element</span></span>  
<span data-ttu-id="634f1-105">\<Library> 元素</span><span class="sxs-lookup"><span data-stu-id="634f1-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="634f1-106">语法</span><span class="sxs-lookup"><span data-stu-id="634f1-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="634f1-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="634f1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="634f1-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="634f1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="634f1-109">特性</span><span class="sxs-lookup"><span data-stu-id="634f1-109">Attributes</span></span>  
  
|<span data-ttu-id="634f1-110">特性</span><span class="sxs-lookup"><span data-stu-id="634f1-110">Attribute</span></span>|<span data-ttu-id="634f1-111">描述</span><span class="sxs-lookup"><span data-stu-id="634f1-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="634f1-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="634f1-112">Required attribute.</span></span> <span data-ttu-id="634f1-113">指定一个程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="634f1-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="634f1-114">这个 `<Library>` 元素的子元素为在这个程序集中找到的类型和类型成员定义运行时反射策略。</span><span class="sxs-lookup"><span data-stu-id="634f1-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="634f1-115">Name 特性</span><span class="sxs-lookup"><span data-stu-id="634f1-115">Name attribute</span></span>  
  
|<span data-ttu-id="634f1-116">值</span><span class="sxs-lookup"><span data-stu-id="634f1-116">Value</span></span>|<span data-ttu-id="634f1-117">描述</span><span class="sxs-lookup"><span data-stu-id="634f1-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="634f1-118">assembly_name</span><span class="sxs-lookup"><span data-stu-id="634f1-118">*assembly_name*</span></span>|<span data-ttu-id="634f1-119">程序集的简单名称，不要包含文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="634f1-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="634f1-120">此特性对应 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="634f1-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="634f1-121">例如，一个名为 Extensions.dll 的程序集的名称为“Extensions”。</span><span class="sxs-lookup"><span data-stu-id="634f1-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="634f1-122">参阅“备注”部分，了解支持对来自程序集的元数据有条件包含的 assembly_name 的一种特殊形式。</span><span class="sxs-lookup"><span data-stu-id="634f1-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="634f1-123">子元素</span><span class="sxs-lookup"><span data-stu-id="634f1-123">Child Elements</span></span>  
  
|<span data-ttu-id="634f1-124">元素</span><span class="sxs-lookup"><span data-stu-id="634f1-124">Element</span></span>|<span data-ttu-id="634f1-125">描述</span><span class="sxs-lookup"><span data-stu-id="634f1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="634f1-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="634f1-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="634f1-127">将策略应用到特定程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="634f1-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="634f1-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="634f1-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="634f1-129">将策略应用到特定命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="634f1-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="634f1-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="634f1-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="634f1-131">将策略应用到一个特定类型，例如一个类或结构。</span><span class="sxs-lookup"><span data-stu-id="634f1-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="634f1-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="634f1-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="634f1-133">将策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="634f1-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="634f1-134">例如，一个 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 元素可用于为一个 `List<String>` 类型定义策略。</span><span class="sxs-lookup"><span data-stu-id="634f1-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="634f1-135">父元素</span><span class="sxs-lookup"><span data-stu-id="634f1-135">Parent Elements</span></span>  
  
|<span data-ttu-id="634f1-136">元素</span><span class="sxs-lookup"><span data-stu-id="634f1-136">Element</span></span>|<span data-ttu-id="634f1-137">描述</span><span class="sxs-lookup"><span data-stu-id="634f1-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="634f1-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="634f1-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="634f1-139">运行时指令文件的根元素。</span><span class="sxs-lookup"><span data-stu-id="634f1-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="634f1-140">备注</span><span class="sxs-lookup"><span data-stu-id="634f1-140">Remarks</span></span>  
 <span data-ttu-id="634f1-141">[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 元素可包括零个、一个或多个 `<Library>` 元素。</span><span class="sxs-lookup"><span data-stu-id="634f1-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="634f1-142">`<Library>` 元素充当容器，用来定义其元数据在运行时间需要存在的程序元素；此元素不表示策略。</span><span class="sxs-lookup"><span data-stu-id="634f1-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="634f1-143">在编译时间，编译器工具仅搜索由 `<Library>` 元素指定的库，以查找其子元素识别出的程序元素。</span><span class="sxs-lookup"><span data-stu-id="634f1-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="634f1-144">相比而言，编译器工具搜索 .NET Framework 核心库等所有库，以查找由 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 元素识别出的子元素。</span><span class="sxs-lookup"><span data-stu-id="634f1-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="634f1-145">`<Library>` 指令可以有条件地使用。</span><span class="sxs-lookup"><span data-stu-id="634f1-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="634f1-146">如果 `<Library>` 元素名称的前后都有一个星号 (*)，`<Library>` 指令仅在星号之间指定的程序库被该应用引用时才有效。</span><span class="sxs-lookup"><span data-stu-id="634f1-146">If the name of the `<Library>` element starts and ends with an asterisk (*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="634f1-147">例如，以下运行时指令仅在 Utillities.dll 程序库被应用引用时才适用。</span><span class="sxs-lookup"><span data-stu-id="634f1-147">For example, the following runtime directive applies only if the Utillities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="634f1-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="634f1-148">See Also</span></span>  
 [<span data-ttu-id="634f1-149">\<应用程序 > 元素</span><span class="sxs-lookup"><span data-stu-id="634f1-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 [<span data-ttu-id="634f1-150">\<指令 > 元素</span><span class="sxs-lookup"><span data-stu-id="634f1-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 [<span data-ttu-id="634f1-151">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="634f1-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="634f1-152">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="634f1-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
