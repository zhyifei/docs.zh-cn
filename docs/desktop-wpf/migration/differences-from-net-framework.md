---
title: .NET 框架和 .NET 核心之间的差异
description: 描述 Windows 演示基础 （WPF） 的 .NET 框架实现和 .NET 核心 WPF 之间的差异。 迁移应用时，应考虑这些不兼容因素。
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 341e576f17c522fbcbb9c417176e9d4a13ab1b18
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021843"
---
# <a name="differences-in-wpf"></a><span data-ttu-id="a5a37-104">WPF 的差异</span><span class="sxs-lookup"><span data-stu-id="a5a37-104">Differences in WPF</span></span>

<span data-ttu-id="a5a37-105">本文介绍了 .NET 核心和 .NET 框架上的 Windows 演示基础 （WPF） 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a5a37-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="a5a37-106">.NET Core 的 WPF 是从原始 WPF 为 .NET 框架源代码分叉的[开源框架](https://github.com/dotnet/wpf)。</span><span class="sxs-lookup"><span data-stu-id="a5a37-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="a5a37-107">.NET 框架有几个功能，而 .NET Core 不支持这些功能。</span><span class="sxs-lookup"><span data-stu-id="a5a37-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="a5a37-108">有关不支持的技术的详细信息，请参阅[.NET 框架技术在 .NET Core 上不可用](../../core/porting/net-framework-tech-unavailable.md)。</span><span class="sxs-lookup"><span data-stu-id="a5a37-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="a5a37-109">SDK 风格的项目</span><span class="sxs-lookup"><span data-stu-id="a5a37-109">SDK-style projects</span></span>

<span data-ttu-id="a5a37-110">.NET Core 使用 SDK 风格的项目文件。</span><span class="sxs-lookup"><span data-stu-id="a5a37-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="a5a37-111">这些项目文件不同于 Visual Studio 管理的传统 .NET 框架项目文件。</span><span class="sxs-lookup"><span data-stu-id="a5a37-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="a5a37-112">要将 .NET 框架 WPF 应用迁移到 .NET Core，必须转换项目。</span><span class="sxs-lookup"><span data-stu-id="a5a37-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="a5a37-113">有关详细信息，请参阅将[WPF 应用迁移到 .NET 核心 3.0](convert-project-from-net-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="a5a37-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="a5a37-114">NuGet 包引用</span><span class="sxs-lookup"><span data-stu-id="a5a37-114">NuGet package references</span></span>

<span data-ttu-id="a5a37-115">如果您的 .NET Framework 应用在包中列出了其 NuGet 依赖项 *。* [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)</span><span class="sxs-lookup"><span data-stu-id="a5a37-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="a5a37-116">在可视化工作室中，打开 **"解决方案资源管理器"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="a5a37-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="a5a37-117">在 WPF 项目中，右键单击**包.config** > **迁移包。config 到包参考**。</span><span class="sxs-lookup"><span data-stu-id="a5a37-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![升级到包参考](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="a5a37-119">将显示一个对话框，显示计算的顶级 NuGet 依赖项，并询问应将哪些其他 NuGet 包提升到顶层。</span><span class="sxs-lookup"><span data-stu-id="a5a37-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="a5a37-120">选择 **"确定**"，*包.config*文件将从项目中删除，`<PackageReference>`元素将添加到项目文件中。</span><span class="sxs-lookup"><span data-stu-id="a5a37-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="a5a37-121">当项目使用`<PackageReference>`时，包不会存储在 *"包"* 文件夹中本地，它们存储在全局。</span><span class="sxs-lookup"><span data-stu-id="a5a37-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="a5a37-122">打开项目文件并删除引用`<Analyzer>`*"包"* 文件夹的任何元素。</span><span class="sxs-lookup"><span data-stu-id="a5a37-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="a5a37-123">这些分析器会自动包含在 NuGet 包引用中。</span><span class="sxs-lookup"><span data-stu-id="a5a37-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="a5a37-124">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="a5a37-124">Code Access Security</span></span>

<span data-ttu-id="a5a37-125">.NET 核心或 .NET Core 的 WPF 不支持代码访问安全性 （CAS）。</span><span class="sxs-lookup"><span data-stu-id="a5a37-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="a5a37-126">所有 CAS 相关功能均以完全信任为假设处理。</span><span class="sxs-lookup"><span data-stu-id="a5a37-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="a5a37-127">.NET Core 的 WPF 删除 CAS 相关代码。</span><span class="sxs-lookup"><span data-stu-id="a5a37-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="a5a37-128">这些类型的公共 API 表面仍然存在，以确保对这些类型的调用成功。</span><span class="sxs-lookup"><span data-stu-id="a5a37-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="a5a37-129">公开定义的 CAS 相关类型从 WPF 程序集移出并移动到 Core .NET 库程序集中。</span><span class="sxs-lookup"><span data-stu-id="a5a37-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the Core .NET library assemblies.</span></span> <span data-ttu-id="a5a37-130">WPF 程序集具有类型转发设置为移动类型的新位置。</span><span class="sxs-lookup"><span data-stu-id="a5a37-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="a5a37-131">源程序集</span><span class="sxs-lookup"><span data-stu-id="a5a37-131">Source assembly</span></span> | <span data-ttu-id="a5a37-132">目标程序集</span><span class="sxs-lookup"><span data-stu-id="a5a37-132">Target assembly</span></span> | <span data-ttu-id="a5a37-133">类型</span><span class="sxs-lookup"><span data-stu-id="a5a37-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="a5a37-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="a5a37-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="a5a37-135">*系统.安全.权限.dll*</span><span class="sxs-lookup"><span data-stu-id="a5a37-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="a5a37-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="a5a37-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="a5a37-137">*系统.安全.权限.dll*</span><span class="sxs-lookup"><span data-stu-id="a5a37-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="a5a37-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="a5a37-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="a5a37-139">*系统.Windows.扩展.dll*</span><span class="sxs-lookup"><span data-stu-id="a5a37-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="a5a37-140">为了尽量减少移植摩擦，在类型中保留了存储和检索与以下属性相关的信息的功能`XamlAccessLevel`。</span><span class="sxs-lookup"><span data-stu-id="a5a37-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="a5a37-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a5a37-141">Next steps</span></span>

- [<span data-ttu-id="a5a37-142">了解如何将 .NET 框架 WPF 应用移植到 .NET 核心。</span><span class="sxs-lookup"><span data-stu-id="a5a37-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
