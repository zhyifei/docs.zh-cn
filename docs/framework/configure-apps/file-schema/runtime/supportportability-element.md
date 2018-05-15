---
title: '&lt;supportPortability&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a8a454919a195a0f0c03ed6890e51b2723f64fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltsupportportabilitygt-element"></a><span data-ttu-id="b45f6-102">&lt;supportPortability&gt;元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-102">&lt;supportPortability&gt; Element</span></span>
<span data-ttu-id="b45f6-103">通过禁用将程序集视为等效于应用程序可移植性用途的默认行为来指定应用程序可以在两种不同的 .NET Framework 实现中引用同一程序集。</span><span class="sxs-lookup"><span data-stu-id="b45f6-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="b45f6-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-104">\<configuration> Element</span></span>  
<span data-ttu-id="b45f6-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-105">\<runtime> Element</span></span>  
<span data-ttu-id="b45f6-106">\<assemblyBinding > 元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="b45f6-107">\<supportPortability > 元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b45f6-108">语法</span><span class="sxs-lookup"><span data-stu-id="b45f6-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b45f6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b45f6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b45f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b45f6-111">特性</span><span class="sxs-lookup"><span data-stu-id="b45f6-111">Attributes</span></span>  
  
|<span data-ttu-id="b45f6-112">特性</span><span class="sxs-lookup"><span data-stu-id="b45f6-112">Attribute</span></span>|<span data-ttu-id="b45f6-113">描述</span><span class="sxs-lookup"><span data-stu-id="b45f6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b45f6-114">PKT</span><span class="sxs-lookup"><span data-stu-id="b45f6-114">PKT</span></span>|<span data-ttu-id="b45f6-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="b45f6-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="b45f6-116">以字符串形式指定的受影响的程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="b45f6-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="b45f6-117">enabled</span><span class="sxs-lookup"><span data-stu-id="b45f6-117">enabled</span></span>|<span data-ttu-id="b45f6-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="b45f6-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b45f6-119">指定是否应启用对指定的.NET Framework 程序集的实现之间的可移植性的支持。</span><span class="sxs-lookup"><span data-stu-id="b45f6-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b45f6-120">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="b45f6-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="b45f6-121">值</span><span class="sxs-lookup"><span data-stu-id="b45f6-121">Value</span></span>|<span data-ttu-id="b45f6-122">描述</span><span class="sxs-lookup"><span data-stu-id="b45f6-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b45f6-123">true</span><span class="sxs-lookup"><span data-stu-id="b45f6-123">true</span></span>|<span data-ttu-id="b45f6-124">启用对指定的.NET Framework 程序集的实现之间的可移植性支持。</span><span class="sxs-lookup"><span data-stu-id="b45f6-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="b45f6-125">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="b45f6-125">This is the default.</span></span>|  
|<span data-ttu-id="b45f6-126">False</span><span class="sxs-lookup"><span data-stu-id="b45f6-126">false</span></span>|<span data-ttu-id="b45f6-127">禁用指定的.NET Framework 程序集的实现之间的可移植性的支持。</span><span class="sxs-lookup"><span data-stu-id="b45f6-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="b45f6-128">这使应用程序具有对指定的程序集的多个实现的引用。</span><span class="sxs-lookup"><span data-stu-id="b45f6-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b45f6-129">子元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-129">Child Elements</span></span>  
 <span data-ttu-id="b45f6-130">无。</span><span class="sxs-lookup"><span data-stu-id="b45f6-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b45f6-131">父元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b45f6-132">元素</span><span class="sxs-lookup"><span data-stu-id="b45f6-132">Element</span></span>|<span data-ttu-id="b45f6-133">描述</span><span class="sxs-lookup"><span data-stu-id="b45f6-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b45f6-134">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b45f6-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b45f6-135">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="b45f6-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="b45f6-136">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="b45f6-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b45f6-137">备注</span><span class="sxs-lookup"><span data-stu-id="b45f6-137">Remarks</span></span>  
 <span data-ttu-id="b45f6-138">开头[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，支持将自动提供给应用程序可以使用的.NET Framework 中，两个实现任一例如.NET Framework 实现或.NET 框架，用于 Silverlight 的实现。</span><span class="sxs-lookup"><span data-stu-id="b45f6-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="b45f6-139">程序集联编程序将特定的.NET Framework 程序集的两个实现视为等效项。</span><span class="sxs-lookup"><span data-stu-id="b45f6-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="b45f6-140">在少数情况下，此应用程序可移植性功能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="b45f6-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="b45f6-141">在这些情况下，`<supportPortability>`元素可以用来禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="b45f6-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="b45f6-142">其中一种方案是具有以引用的.NET Framework 实现和.NET Framework Silverlight 实现的特定引用程序集的程序集。</span><span class="sxs-lookup"><span data-stu-id="b45f6-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="b45f6-143">例如，编写 Windows Presentation Foundation (WPF) 中的 XAML 设计器可能需要引用这两个的 WPF 桌面实现，用于设计器的用户界面，并在 Silverlight 实现中包含的 WPF 的子集。</span><span class="sxs-lookup"><span data-stu-id="b45f6-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="b45f6-144">默认情况下，单独引用会导致编译器错误，因为程序集绑定将这两个程序集视为等效。</span><span class="sxs-lookup"><span data-stu-id="b45f6-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="b45f6-145">此元素禁用默认行为，并允许编译成功。</span><span class="sxs-lookup"><span data-stu-id="b45f6-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b45f6-146">为了使编译器将信息传递到公共语言运行时的程序集绑定逻辑，必须使用`/appconfig`编译器选项来指定包含此元素的 app.config 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b45f6-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b45f6-147">示例</span><span class="sxs-lookup"><span data-stu-id="b45f6-147">Example</span></span>  
 <span data-ttu-id="b45f6-148">以下示例启用应用程序具有对.NET Framework 实现和 Silverlight 实现这两个实现中存在的任何.NET Framework 程序集的.NET Framework 的引用。</span><span class="sxs-lookup"><span data-stu-id="b45f6-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="b45f6-149">`/appconfig`编译器选项必须用于指定此 app.config 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b45f6-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b45f6-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="b45f6-150">See Also</span></span>  
 [<span data-ttu-id="b45f6-151">/appconfig （C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="b45f6-151">/appconfig (C# Compiler Options)</span></span>](http://msdn.microsoft.com/library/ee523958.aspx)  
 [<span data-ttu-id="b45f6-152">.NET framework 程序集统一概述</span><span class="sxs-lookup"><span data-stu-id="b45f6-152">.NET Framework Assembly Unification Overview</span></span>](http://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
