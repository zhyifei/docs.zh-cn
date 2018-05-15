---
title: 设置程序集特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af1db244f02701e6da1604ec406f4fb2940f8f78
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="setting-assembly-attributes"></a><span data-ttu-id="ec32b-102">设置程序集特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-102">Setting Assembly Attributes</span></span>
<span data-ttu-id="ec32b-103">程序集特性是提供程序集相关信息的值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-103">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="ec32b-104">特性分为以下几组信息：</span><span class="sxs-lookup"><span data-stu-id="ec32b-104">The attributes are divided into the following sets of information:</span></span>  
  
-   <span data-ttu-id="ec32b-105">程序集标识特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-105">Assembly identity attributes.</span></span>  
  
-   <span data-ttu-id="ec32b-106">信息性特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-106">Informational attributes.</span></span>  
  
-   <span data-ttu-id="ec32b-107">程序集清单特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-107">Assembly manifest attributes.</span></span>  
  
-   <span data-ttu-id="ec32b-108">强名称特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-108">Strong name attributes.</span></span>  
  
## <a name="assembly-identity-attributes"></a><span data-ttu-id="ec32b-109">程序集标识特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-109">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="ec32b-110">三个特性与强名称（如果适用）组合起来可以确定程序集的标识：名称、版本和区域性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-110">Three attributes, together with a strong name (if applicable), determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="ec32b-111">这些特性构成程序集的完整名称，在代码中引用程序集时必需使用。</span><span class="sxs-lookup"><span data-stu-id="ec32b-111">These attributes form the full name of the assembly and are required when referencing the assembly in code.</span></span> <span data-ttu-id="ec32b-112">特性可用于设置程序集的版本和区域性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-112">You can use attributes to set an assembly's version and culture.</span></span> <span data-ttu-id="ec32b-113">编译器或 [程序集链接器 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 依据包含程序集清单的文件在创建该程序集时设置名称值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-113">The compiler or the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) sets the name value when the assembly is created, based on the file containing the assembly manifest.</span></span>  
  
 <span data-ttu-id="ec32b-114">下表介绍了版本和区域性特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-114">The following table describes the version and culture attributes.</span></span>  
  
|<span data-ttu-id="ec32b-115">程序集标识特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-115">Assembly identity attribute</span></span>|<span data-ttu-id="ec32b-116">描述</span><span class="sxs-lookup"><span data-stu-id="ec32b-116">Description</span></span>|  
|---------------------------------|-----------------|  
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="ec32b-117">表示程序集所支持的区域性的枚举字段。</span><span class="sxs-lookup"><span data-stu-id="ec32b-117">Enumerated field indicating the culture that the assembly supports.</span></span> <span data-ttu-id="ec32b-118">程序集还可以指定区域性独立性，表示它包含默认区域性的资源。</span><span class="sxs-lookup"><span data-stu-id="ec32b-118">An assembly can also specify culture independence, indicating that it contains the resources for the default culture.</span></span> <span data-ttu-id="ec32b-119">注意：对于区域性特性未设置为 null 的任何程序集，运行时都会将它们视为附属程序集。</span><span class="sxs-lookup"><span data-stu-id="ec32b-119">**Note:**  The runtime treats any assembly that does not have the culture attribute set to null as a satellite assembly.</span></span> <span data-ttu-id="ec32b-120">此类程序集需遵循附属程序集绑定规则。</span><span class="sxs-lookup"><span data-stu-id="ec32b-120">Such assemblies are subject to satellite assembly binding rules.</span></span> <span data-ttu-id="ec32b-121">有关更多信息，请参阅 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="ec32b-121">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="ec32b-122">设置程序集特性（例如是否可以并行运行程序集）的值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-122">Value that sets assembly attributes, such as whether the assembly can be run side by side.</span></span>|  
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="ec32b-123">以 *主版本*.*次版本*.*内部版本*.*修订版本* 为格式的数值（例如 2.4.0.0）。</span><span class="sxs-lookup"><span data-stu-id="ec32b-123">Numeric value in the format *major*.*minor*.*build*.*revision* (for example, 2.4.0.0).</span></span> <span data-ttu-id="ec32b-124">公共语言运行时使用此值在强名称程序集中执行绑定操作。</span><span class="sxs-lookup"><span data-stu-id="ec32b-124">The common language runtime uses this value to perform binding operations in strong-named assemblies.</span></span> <span data-ttu-id="ec32b-125">注意：如果 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 特性不适用于程序集，则 <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>、<xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> 属性将使用由 <xref:System.Reflection.AssemblyVersionAttribute> 特性指定的版本号。</span><span class="sxs-lookup"><span data-stu-id="ec32b-125">**Note:**  If the <xref:System.Reflection.AssemblyInformationalVersionAttribute> attribute is not applied to an assembly, the version number specified by the <xref:System.Reflection.AssemblyVersionAttribute> attribute is used by the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>, and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|  
  
 <span data-ttu-id="ec32b-126">下面的示例演示了如何将版本和区域性特性应用到程序集中。</span><span class="sxs-lookup"><span data-stu-id="ec32b-126">The following code example shows how to apply the version and culture attributes to an assembly.</span></span>  
  
 [!code-cpp[AssemblyDelaySignAttribute#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#3)]
 [!code-csharp[AssemblyDelaySignAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#3)]
 [!code-vb[AssemblyDelaySignAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#3)]  
  
## <a name="informational-attributes"></a><span data-ttu-id="ec32b-127">信息性特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-127">Informational Attributes</span></span>  
 <span data-ttu-id="ec32b-128">信息性特性可用于提供程序集的其他公司或产品信息。</span><span class="sxs-lookup"><span data-stu-id="ec32b-128">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="ec32b-129">下表介绍了可应用于程序集的信息性特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-129">The following table describes the informational attributes you can apply to an assembly.</span></span>  
  
|<span data-ttu-id="ec32b-130">信息性特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-130">Informational attribute</span></span>|<span data-ttu-id="ec32b-131">描述</span><span class="sxs-lookup"><span data-stu-id="ec32b-131">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="ec32b-132">指定公司名称的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-132">String value specifying a company name.</span></span>|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="ec32b-133">指定版权信息的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-133">String value specifying copyright information.</span></span>|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="ec32b-134">指定 Win32 文件版本号的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-134">String value specifying the Win32 file version number.</span></span> <span data-ttu-id="ec32b-135">通常默认为程序集版本。</span><span class="sxs-lookup"><span data-stu-id="ec32b-135">This normally defaults to the assembly version.</span></span>|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="ec32b-136">指定公共语言运行时未使用的版本信息（例如完整的产品版本号）的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-136">String value specifying version information that is not used by the common language runtime, such as a full product version number.</span></span> <span data-ttu-id="ec32b-137">注意：如果将此特性应用于程序集，可在运行时通过使用 <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> 属性获得其指定的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec32b-137">**Note:**  If this attribute is applied to an assembly, the string it specifies can be obtained at run time by using the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ec32b-138">此字符串还用于 <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> 属性所提供的路径和注册表项。</span><span class="sxs-lookup"><span data-stu-id="ec32b-138">The string is also used in the path and registry key provided by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|  
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="ec32b-139">指定产品信息的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-139">String value specifying product information.</span></span>|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="ec32b-140">指定商标信息的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-140">String value specifying trademark information.</span></span>|  
  
 <span data-ttu-id="ec32b-141">这些特性可以出现在程序集的 Windows 属性页上，或使用 **/win32res** 编译器选项重写，以指定自己的 Win32 资源文件。</span><span class="sxs-lookup"><span data-stu-id="ec32b-141">These attributes can appear on the Windows Properties page of the assembly, or they can be overridden using the **/win32res** compiler option to specify your own Win32 resource file.</span></span>  
  
## <a name="assembly-manifest-attributes"></a><span data-ttu-id="ec32b-142">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-142">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="ec32b-143">程序集清单特性可用于在程序集清单中提供标题、说明、默认别名和配置等信息。</span><span class="sxs-lookup"><span data-stu-id="ec32b-143">You can use assembly manifest attributes to provide information in the assembly manifest, including title, description, the default alias, and configuration.</span></span> <span data-ttu-id="ec32b-144">下表介绍了程序集清单特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-144">The following table describes the assembly manifest attributes.</span></span>  
  
|<span data-ttu-id="ec32b-145">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-145">Assembly manifest attribute</span></span>|<span data-ttu-id="ec32b-146">描述</span><span class="sxs-lookup"><span data-stu-id="ec32b-146">Description</span></span>|  
|---------------------------------|-----------------|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="ec32b-147">表示程序集配置（如零售或调试）的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-147">String value indicating the configuration of the assembly, such as Retail or Debug.</span></span> <span data-ttu-id="ec32b-148">运行时不使用此规则。</span><span class="sxs-lookup"><span data-stu-id="ec32b-148">The runtime does not use this value.</span></span>|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="ec32b-149">指定引用程序集所用的默认别名的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-149">String value specifying a default alias to be used by referencing assemblies.</span></span> <span data-ttu-id="ec32b-150">此值会在程序集本身的名称不友好（例如 GUID 值）的情况下提供一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="ec32b-150">This value provides a friendly name when the name of the assembly itself is not friendly (such as a GUID value).</span></span> <span data-ttu-id="ec32b-151">此值还可用于完整程序集名称的缩写。</span><span class="sxs-lookup"><span data-stu-id="ec32b-151">This value can also be used as a short form of the full assembly name.</span></span>|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="ec32b-152">指定描述程序集性质和用途简短说明的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-152">String value specifying a short description that summarizes the nature and purpose of the assembly.</span></span>|  
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="ec32b-153">指定程序集的友好名称的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-153">String value specifying a friendly name for the assembly.</span></span> <span data-ttu-id="ec32b-154">例如，名为 comdlg 的程序集的标题可能为“Microsoft 通用对话框控件”。</span><span class="sxs-lookup"><span data-stu-id="ec32b-154">For example, an assembly named comdlg might have the title Microsoft Common Dialog Control.</span></span>|  
  
## <a name="strong-name-attributes"></a><span data-ttu-id="ec32b-155">强名称特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-155">Strong Name Attributes</span></span>  
 <span data-ttu-id="ec32b-156">强名称特性可用于设置程序集的强名称。</span><span class="sxs-lookup"><span data-stu-id="ec32b-156">You can use strong name attributes to set a strong name for an assembly.</span></span> <span data-ttu-id="ec32b-157">下表介绍了强名称特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-157">The following table describes the strong name attributes.</span></span>  
  
|<span data-ttu-id="ec32b-158">强名称特性</span><span class="sxs-lookup"><span data-stu-id="ec32b-158">Strong name attributes</span></span>|<span data-ttu-id="ec32b-159">描述</span><span class="sxs-lookup"><span data-stu-id="ec32b-159">Description</span></span>|  
|----------------------------|-----------------|  
|<xref:System.Reflection.AssemblyDelaySignAttribute>|<span data-ttu-id="ec32b-160">表示正在使用延迟签名的布尔值。</span><span class="sxs-lookup"><span data-stu-id="ec32b-160">Boolean value indicating that delay signing is being used.</span></span>|  
|<xref:System.Reflection.AssemblyKeyFileAttribute>|<span data-ttu-id="ec32b-161">表示文件名称的字符串值，该文件包含公钥（如果使用延迟签名）或同时包含作为参数传递给此特性的构造函数的公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="ec32b-161">String value indicating the name of the file that contains either the public key (if using delay signing) or both the public and private keys passed as a parameter to the constructor of this attribute.</span></span> <span data-ttu-id="ec32b-162">请注意文件名相对于输出文件路径（.exe 或.dll），而不是源文件路径。</span><span class="sxs-lookup"><span data-stu-id="ec32b-162">Note that the file name is relative to the output file path (the .exe or .dll), not the source file path.</span></span>|  
|<xref:System.Reflection.AssemblyKeyNameAttribute>|<span data-ttu-id="ec32b-163">表示包含作为参数传递给此特性的构造函数的密钥对的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="ec32b-163">Indicates the key container that contains the key pair passed as a parameter to the constructor of this attribute.</span></span>|  
  
 <span data-ttu-id="ec32b-164">以下代码示例介绍了使用延迟签名用公钥文件 `myKey.snk`创建强名称程序集时应用的特性。</span><span class="sxs-lookup"><span data-stu-id="ec32b-164">The following code example shows the attributes to apply when using delay signing to create a strong-named assembly with a public key file called `myKey.snk`.</span></span>  
  
 [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
 [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
 [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ec32b-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec32b-165">See Also</span></span>  
 [<span data-ttu-id="ec32b-166">创建程序集</span><span class="sxs-lookup"><span data-stu-id="ec32b-166">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="ec32b-167">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="ec32b-167">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
