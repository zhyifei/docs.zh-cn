---
title: C# 保留的特性：全局属性
ms.date: 04/09/2020
description: 特性提供编译器用来了解程序的更多语义的元数据
ms.openlocfilehash: f855f32cd7349da34ffbd20fededdf42c3023938
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389804"
---
# <a name="reserved-attributes-assembly-level-attributes"></a><span data-ttu-id="24875-103">保留的特性：程序集级别特性</span><span class="sxs-lookup"><span data-stu-id="24875-103">Reserved attributes: Assembly level attributes</span></span>

<span data-ttu-id="24875-104">大多数特性应用于特定语言元素，如类或方法；但是，一些特性是全局特性 - 它们应用于整个程序集或模块。</span><span class="sxs-lookup"><span data-stu-id="24875-104">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="24875-105">例如，<xref:System.Reflection.AssemblyVersionAttribute> 属性可用于将版本信息嵌入程序集，如下所示：</span><span class="sxs-lookup"><span data-stu-id="24875-105">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>

```csharp
[assembly: AssemblyVersion("1.0.0.0")]
```

<span data-ttu-id="24875-106">全局特性出现在源代码中任何顶级 `using` 指令之后和任何类型、模块或命名空间声明之前。</span><span class="sxs-lookup"><span data-stu-id="24875-106">Global attributes appear in the source code after any top level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="24875-107">全局特性可以出现在多个源文件中，但必须在单个编译过程中编译这些文件。</span><span class="sxs-lookup"><span data-stu-id="24875-107">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="24875-108">Visual Studio 将全局特性添加到 .NET Framework 项目中的 AssemblyInfo.cs 文件中。</span><span class="sxs-lookup"><span data-stu-id="24875-108">Visual Studio adds global attributes to the AssemblyInfo.cs file in .NET Framework projects.</span></span> <span data-ttu-id="24875-109">这些特性不会添加到 .NET Core 项目中。</span><span class="sxs-lookup"><span data-stu-id="24875-109">These attributes aren't added to .NET Core projects.</span></span>

<span data-ttu-id="24875-110">程序集特性是提供程序集相关信息的值。</span><span class="sxs-lookup"><span data-stu-id="24875-110">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="24875-111">它们分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="24875-111">They fall into the following categories:</span></span>

- <span data-ttu-id="24875-112">程序集标识特性</span><span class="sxs-lookup"><span data-stu-id="24875-112">Assembly identity attributes</span></span>
- <span data-ttu-id="24875-113">信息性特性</span><span class="sxs-lookup"><span data-stu-id="24875-113">Informational attributes</span></span>
- <span data-ttu-id="24875-114">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="24875-114">Assembly manifest attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="24875-115">程序集标识特性</span><span class="sxs-lookup"><span data-stu-id="24875-115">Assembly identity attributes</span></span>

<span data-ttu-id="24875-116">三个特性（与强名称（如果适用））组合起来可以确定程序集的标识：名称、版本和区域性。</span><span class="sxs-lookup"><span data-stu-id="24875-116">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="24875-117">这些特性构成程序集的全名，在代码中引用程序集时必需使用。</span><span class="sxs-lookup"><span data-stu-id="24875-117">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="24875-118">可使用特性设置程序集的版本和区域性。</span><span class="sxs-lookup"><span data-stu-id="24875-118">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="24875-119">但是，创建程序集时，由编译器、[程序集信息对话框](/visualstudio/ide/reference/assembly-information-dialog-box)中的 Visual Studio IDE 或程序集链接器 (Al.exe) 设置名称值。</span><span class="sxs-lookup"><span data-stu-id="24875-119">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created.</span></span> <span data-ttu-id="24875-120">程序集名称基于程序集清单。</span><span class="sxs-lookup"><span data-stu-id="24875-120">The assembly name is based on the assembly manifest.</span></span> <span data-ttu-id="24875-121"><xref:System.Reflection.AssemblyFlagsAttribute> 属性指定程序集的多个副本是否可以共存。</span><span class="sxs-lookup"><span data-stu-id="24875-121">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>

<span data-ttu-id="24875-122">下表显示标识特性。</span><span class="sxs-lookup"><span data-stu-id="24875-122">The following table shows the identity attributes.</span></span>

|<span data-ttu-id="24875-123">特性</span><span class="sxs-lookup"><span data-stu-id="24875-123">Attribute</span></span>|<span data-ttu-id="24875-124">目标</span><span class="sxs-lookup"><span data-stu-id="24875-124">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="24875-125">指定程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="24875-125">Specifies the version of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="24875-126">指定程序集支持的区域性。</span><span class="sxs-lookup"><span data-stu-id="24875-126">Specifies which culture the assembly supports.</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="24875-127">指定程序集是否支持在同一计算机上、同一进程中或同一应用程序域中并行执行。</span><span class="sxs-lookup"><span data-stu-id="24875-127">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|

## <a name="informational-attributes"></a><span data-ttu-id="24875-128">信息性特性</span><span class="sxs-lookup"><span data-stu-id="24875-128">Informational attributes</span></span>

<span data-ttu-id="24875-129">你可使用信息性特性为程序集提供其他公司或产品信息。</span><span class="sxs-lookup"><span data-stu-id="24875-129">You use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="24875-130">下表显示 <xref:System.Reflection?displayProperty=nameWithType> 命名空间中定义的信息性属性。</span><span class="sxs-lookup"><span data-stu-id="24875-130">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="24875-131">特性</span><span class="sxs-lookup"><span data-stu-id="24875-131">Attribute</span></span>|<span data-ttu-id="24875-132">目标</span><span class="sxs-lookup"><span data-stu-id="24875-132">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="24875-133">指定程序集清单的产品名称。</span><span class="sxs-lookup"><span data-stu-id="24875-133">Specifies a product name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="24875-134">指定程序集清单的商标。</span><span class="sxs-lookup"><span data-stu-id="24875-134">Specifies a trademark for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="24875-135">为程序集清单指定信息性版本。</span><span class="sxs-lookup"><span data-stu-id="24875-135">Specifies an informational version for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="24875-136">为程序集清单指定公司名称。</span><span class="sxs-lookup"><span data-stu-id="24875-136">Specifies a company name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="24875-137">定义为程序集清单指定版权的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="24875-137">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="24875-138">设置 Win32 文件版本资源的特定版本号。</span><span class="sxs-lookup"><span data-stu-id="24875-138">Sets a specific version number for the Win32 file version resource.</span></span>|
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="24875-139">指示程序集是否符合公共语言规范 (CLS)。</span><span class="sxs-lookup"><span data-stu-id="24875-139">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="24875-140">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="24875-140">Assembly manifest attributes</span></span>

<span data-ttu-id="24875-141">程序集清单特性可用于提供程序集清单中的信息。</span><span class="sxs-lookup"><span data-stu-id="24875-141">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="24875-142">特性包括标题、说明、默认别名和配置。</span><span class="sxs-lookup"><span data-stu-id="24875-142">The attributes include title, description, default alias, and configuration.</span></span> <span data-ttu-id="24875-143">下表显示 <xref:System.Reflection?displayProperty=nameWithType> 命名空间中定义的程序集清单属性。</span><span class="sxs-lookup"><span data-stu-id="24875-143">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="24875-144">特性</span><span class="sxs-lookup"><span data-stu-id="24875-144">Attribute</span></span>|<span data-ttu-id="24875-145">目标</span><span class="sxs-lookup"><span data-stu-id="24875-145">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="24875-146">为程序集清单指定程序集标题。</span><span class="sxs-lookup"><span data-stu-id="24875-146">Specifies an assembly title for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="24875-147">为程序集清单指定程序集说明。</span><span class="sxs-lookup"><span data-stu-id="24875-147">Specifies an assembly description for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="24875-148">为程序集清单指定程序集配置（如零售或调试）。</span><span class="sxs-lookup"><span data-stu-id="24875-148">Specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="24875-149">定义程序集清单的友好默认别名</span><span class="sxs-lookup"><span data-stu-id="24875-149">Defines a friendly default alias for an assembly manifest</span></span>|
