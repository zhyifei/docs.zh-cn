---
title: <Library>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc3c85ab99574c96d8a68d4221f218a1340e4122
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049647"
---
# <a name="library-element-net-native"></a><span data-ttu-id="3d481-102">\<库 > 元素（.NET Native）</span><span class="sxs-lookup"><span data-stu-id="3d481-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="3d481-103">定义包含元数据在运行时间可以用于反射的类型和类型成员的程序集。</span><span class="sxs-lookup"><span data-stu-id="3d481-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="3d481-104">\<Directives> 元素</span><span class="sxs-lookup"><span data-stu-id="3d481-104">\<Directives> Element</span></span>  
<span data-ttu-id="3d481-105">\<Library> 元素</span><span class="sxs-lookup"><span data-stu-id="3d481-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d481-106">语法</span><span class="sxs-lookup"><span data-stu-id="3d481-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d481-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3d481-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3d481-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3d481-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d481-109">特性</span><span class="sxs-lookup"><span data-stu-id="3d481-109">Attributes</span></span>  
  
|<span data-ttu-id="3d481-110">特性</span><span class="sxs-lookup"><span data-stu-id="3d481-110">Attribute</span></span>|<span data-ttu-id="3d481-111">描述</span><span class="sxs-lookup"><span data-stu-id="3d481-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="3d481-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3d481-112">Required attribute.</span></span> <span data-ttu-id="3d481-113">指定一个程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3d481-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="3d481-114">这个 `<Library>` 元素的子元素为在这个程序集中找到的类型和类型成员定义运行时反射策略。</span><span class="sxs-lookup"><span data-stu-id="3d481-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="3d481-115">Name 特性</span><span class="sxs-lookup"><span data-stu-id="3d481-115">Name attribute</span></span>  
  
|<span data-ttu-id="3d481-116">值</span><span class="sxs-lookup"><span data-stu-id="3d481-116">Value</span></span>|<span data-ttu-id="3d481-117">描述</span><span class="sxs-lookup"><span data-stu-id="3d481-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d481-118">assembly_name</span><span class="sxs-lookup"><span data-stu-id="3d481-118">*assembly_name*</span></span>|<span data-ttu-id="3d481-119">程序集的简单名称，不要包含文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="3d481-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="3d481-120">此特性对应 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="3d481-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="3d481-121">例如，一个名为 Extensions.dll 的程序集的名称为“Extensions”。</span><span class="sxs-lookup"><span data-stu-id="3d481-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="3d481-122">参阅“备注”部分，了解支持对来自程序集的元数据有条件包含的 assembly_name 的一种特殊形式。</span><span class="sxs-lookup"><span data-stu-id="3d481-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d481-123">子元素</span><span class="sxs-lookup"><span data-stu-id="3d481-123">Child Elements</span></span>  
  
|<span data-ttu-id="3d481-124">元素</span><span class="sxs-lookup"><span data-stu-id="3d481-124">Element</span></span>|<span data-ttu-id="3d481-125">描述</span><span class="sxs-lookup"><span data-stu-id="3d481-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d481-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="3d481-126">\<Assembly></span></span>](assembly-element-net-native.md)|<span data-ttu-id="3d481-127">将策略应用到特定程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="3d481-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="3d481-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="3d481-128">\<Namespace></span></span>](namespace-element-net-native.md)|<span data-ttu-id="3d481-129">将策略应用到特定命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="3d481-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="3d481-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="3d481-130">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="3d481-131">将策略应用到一个特定类型，例如一个类或结构。</span><span class="sxs-lookup"><span data-stu-id="3d481-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="3d481-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="3d481-132">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="3d481-133">将策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="3d481-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="3d481-134">例如，一个 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素可用于为一个 `List<String>` 类型定义策略。</span><span class="sxs-lookup"><span data-stu-id="3d481-134">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d481-135">父元素</span><span class="sxs-lookup"><span data-stu-id="3d481-135">Parent Elements</span></span>  
  
|<span data-ttu-id="3d481-136">元素</span><span class="sxs-lookup"><span data-stu-id="3d481-136">Element</span></span>|<span data-ttu-id="3d481-137">描述</span><span class="sxs-lookup"><span data-stu-id="3d481-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d481-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="3d481-138">\<Directives></span></span>](directives-element-net-native.md)|<span data-ttu-id="3d481-139">运行时指令文件的根元素。</span><span class="sxs-lookup"><span data-stu-id="3d481-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d481-140">备注</span><span class="sxs-lookup"><span data-stu-id="3d481-140">Remarks</span></span>  
 <span data-ttu-id="3d481-141">[\<Directives>](directives-element-net-native.md) 元素可包括零个、一个或多个 `<Library>` 元素。</span><span class="sxs-lookup"><span data-stu-id="3d481-141">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="3d481-142">`<Library>` 元素充当容器，用来定义其元数据在运行时间需要存在的程序元素；此元素不表示策略。</span><span class="sxs-lookup"><span data-stu-id="3d481-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="3d481-143">在编译时间，编译器工具仅搜索由 `<Library>` 元素指定的库，以查找其子元素识别出的程序元素。</span><span class="sxs-lookup"><span data-stu-id="3d481-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="3d481-144">相比而言，编译器工具搜索 .NET Framework 核心库等所有库，以查找由 [\<Application>](application-element-net-native.md) 元素识别出的子元素。</span><span class="sxs-lookup"><span data-stu-id="3d481-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="3d481-145">`<Library>` 指令可以有条件地使用。</span><span class="sxs-lookup"><span data-stu-id="3d481-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="3d481-146">如果`<Library>`元素的名称以星号（\*）开头和结尾，则`<Library>`只有当应用引用星号之间指定的程序集时，指令才会生效。</span><span class="sxs-lookup"><span data-stu-id="3d481-146">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="3d481-147">例如，仅当应用程序引用了实用工具 .dll 程序集时，以下运行时指令才适用。</span><span class="sxs-lookup"><span data-stu-id="3d481-147">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d481-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d481-148">See also</span></span>

- [<span data-ttu-id="3d481-149">\<应用程序 > 元素</span><span class="sxs-lookup"><span data-stu-id="3d481-149">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="3d481-150">\<指令 > 元素</span><span class="sxs-lookup"><span data-stu-id="3d481-150">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="3d481-151">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="3d481-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="3d481-152">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="3d481-152">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
