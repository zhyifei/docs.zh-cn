---
title: <supportPortability> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 63c309a8a93c1d31ed8f73a495cf5154c3590d56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115657"
---
# <a name="supportportability-element"></a><span data-ttu-id="9441f-102">\<supportPortability > 元素</span><span class="sxs-lookup"><span data-stu-id="9441f-102">\<supportPortability> Element</span></span>
<span data-ttu-id="9441f-103">通过禁用将程序集视为等效于应用程序可移植性用途的默认行为来指定应用程序可以在两种不同的 .NET Framework 实现中引用同一程序集。</span><span class="sxs-lookup"><span data-stu-id="9441f-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
<span data-ttu-id="9441f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9441f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9441f-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="9441f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="9441f-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="9441f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="9441f-107">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **\<supportPortability** ></span><span class="sxs-lookup"><span data-stu-id="9441f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9441f-108">语法</span><span class="sxs-lookup"><span data-stu-id="9441f-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9441f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9441f-109">Attributes and Elements</span></span>  

<span data-ttu-id="9441f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9441f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9441f-111">特性</span><span class="sxs-lookup"><span data-stu-id="9441f-111">Attributes</span></span>  
  
|<span data-ttu-id="9441f-112">特性</span><span class="sxs-lookup"><span data-stu-id="9441f-112">Attribute</span></span>|<span data-ttu-id="9441f-113">描述</span><span class="sxs-lookup"><span data-stu-id="9441f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9441f-114">PKT</span><span class="sxs-lookup"><span data-stu-id="9441f-114">PKT</span></span>|<span data-ttu-id="9441f-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="9441f-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="9441f-116">以字符串的形式指定受影响的程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="9441f-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="9441f-117">enabled</span><span class="sxs-lookup"><span data-stu-id="9441f-117">enabled</span></span>|<span data-ttu-id="9441f-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="9441f-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9441f-119">指定是否应启用指定 .NET Framework 程序集的实现之间的可移植性支持。</span><span class="sxs-lookup"><span data-stu-id="9441f-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9441f-120">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="9441f-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="9441f-121">“值”</span><span class="sxs-lookup"><span data-stu-id="9441f-121">Value</span></span>|<span data-ttu-id="9441f-122">描述</span><span class="sxs-lookup"><span data-stu-id="9441f-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9441f-123">true</span><span class="sxs-lookup"><span data-stu-id="9441f-123">true</span></span>|<span data-ttu-id="9441f-124">支持指定 .NET Framework 程序集的实现之间的可移植性。</span><span class="sxs-lookup"><span data-stu-id="9441f-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9441f-125">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="9441f-125">This is the default.</span></span>|  
|<span data-ttu-id="9441f-126">False</span><span class="sxs-lookup"><span data-stu-id="9441f-126">false</span></span>|<span data-ttu-id="9441f-127">禁用支持指定 .NET Framework 程序集的实现之间的可移植性。</span><span class="sxs-lookup"><span data-stu-id="9441f-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9441f-128">这使应用程序可以引用指定程序集的多个实现。</span><span class="sxs-lookup"><span data-stu-id="9441f-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9441f-129">子元素</span><span class="sxs-lookup"><span data-stu-id="9441f-129">Child Elements</span></span>  

<span data-ttu-id="9441f-130">无。</span><span class="sxs-lookup"><span data-stu-id="9441f-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9441f-131">父元素</span><span class="sxs-lookup"><span data-stu-id="9441f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="9441f-132">元素</span><span class="sxs-lookup"><span data-stu-id="9441f-132">Element</span></span>|<span data-ttu-id="9441f-133">描述</span><span class="sxs-lookup"><span data-stu-id="9441f-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9441f-134">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9441f-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9441f-135">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="9441f-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="9441f-136">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="9441f-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9441f-137">备注</span><span class="sxs-lookup"><span data-stu-id="9441f-137">Remarks</span></span>  

<span data-ttu-id="9441f-138">从 .NET Framework 4 开始，将自动为可以使用两种 .NET Framework 实现的应用程序（例如，.NET Framework 实现或 Silverlight 实现的 .NET Framework）提供支持。</span><span class="sxs-lookup"><span data-stu-id="9441f-138">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="9441f-139">特定 .NET Framework 程序集的两个实现被视为等效于程序集联编程序。</span><span class="sxs-lookup"><span data-stu-id="9441f-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="9441f-140">在少数情况下，此应用程序可移植性功能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="9441f-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="9441f-141">在这些情况下，可以使用 `<supportPortability>` 元素禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="9441f-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="9441f-142">这种情况是必须同时引用特定引用程序集的 Silverlight 实现的 .NET Framework 实现和 .NET Framework 的程序集。</span><span class="sxs-lookup"><span data-stu-id="9441f-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="9441f-143">例如，在 Windows Presentation Foundation （WPF）中编写的 XAML 设计器可能需要引用 WPF 桌面实现、设计器的用户界面和 Silverlight 实现中包含的 WPF 的子集。</span><span class="sxs-lookup"><span data-stu-id="9441f-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="9441f-144">默认情况下，单独引用会导致编译器错误，因为程序集绑定将这两个程序集视为等效。</span><span class="sxs-lookup"><span data-stu-id="9441f-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="9441f-145">此元素禁用默认行为，并允许编译成功。</span><span class="sxs-lookup"><span data-stu-id="9441f-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9441f-146">为了使编译器能够将信息传递到公共语言运行时的程序集绑定逻辑，必须使用 `/appconfig` 编译器选项来指定包含此元素的 app.config 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9441f-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9441f-147">示例</span><span class="sxs-lookup"><span data-stu-id="9441f-147">Example</span></span>  

<span data-ttu-id="9441f-148">下面的示例使应用程序能够同时引用在两个实现中都存在的任何 .NET Framework 程序集的 .NET Framework 实现和 Silverlight 实现 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="9441f-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="9441f-149">必须使用 `/appconfig` 编译器选项指定此 app.config 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9441f-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9441f-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="9441f-150">See also</span></span>

- [<span data-ttu-id="9441f-151">-appconfig（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="9441f-151">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="9441f-152">[.NET Framework 程序集统一概述](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9441f-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
