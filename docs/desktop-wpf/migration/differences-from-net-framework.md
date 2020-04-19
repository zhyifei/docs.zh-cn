---
title: .NET 框架和 .NET 核心之间的差异
description: 描述 Windows 演示基础 （WPF） 的 .NET 框架实现和 .NET 核心 WPF 之间的差异。 迁移应用时，应考虑这些不兼容因素。
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 4386654aad205e3c9f2cbd986d7b812e261e737f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "81433132"
---
# <a name="differences-in-wpf"></a>WPF 的差异

本文介绍了 .NET 核心和 .NET 框架上的 Windows 演示基础 （WPF） 之间的差异。 .NET Core 的 WPF 是从原始 WPF 为 .NET 框架源代码分叉的[开源框架](https://github.com/dotnet/wpf)。

.NET 框架有几个功能，而 .NET Core 不支持这些功能。 有关不支持的技术的详细信息，请参阅[.NET 框架技术在 .NET Core 上不可用](../../core/porting/net-framework-tech-unavailable.md)。

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>SDK 风格的项目

.NET Core 使用 SDK 风格的项目文件。 这些项目文件不同于 Visual Studio 管理的传统 .NET 框架项目文件。 要将 .NET 框架 WPF 应用迁移到 .NET Core，必须转换项目。 有关详细信息，请参阅将[WPF 应用迁移到 .NET 核心 3.0](convert-project-from-net-framework.md)。

## <a name="nuget-package-references"></a>NuGet 包引用

如果您的 .NET Framework 应用在包中列出了其 NuGet 依赖项 *。* [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)

1. 在可视化工作室中，打开 **"解决方案资源管理器"** 窗格。
1. 在 WPF 项目中，右键单击**包.config** > **迁移包。config 到包参考**。

![升级到包参考](media/differences-from-net-framework/package-reference-migration.png)

将显示一个对话框，显示计算的顶级 NuGet 依赖项，并询问应将哪些其他 NuGet 包提升到顶层。 选择 **"确定**"，*包.config*文件将从项目中删除，`<PackageReference>`元素将添加到项目文件中。

当项目使用`<PackageReference>`时，包不会存储在 *"包"* 文件夹中本地，它们存储在全局。 打开项目文件并删除引用`<Analyzer>`*"包"* 文件夹的任何元素。 这些分析器会自动包含在 NuGet 包引用中。

## <a name="code-access-security"></a>代码访问安全性

.NET 核心或 .NET Core 的 WPF 不支持代码访问安全性 （CAS）。 所有 CAS 相关功能均以完全信任为假设处理。 .NET Core 的 WPF 删除 CAS 相关代码。 这些类型的公共 API 表面仍然存在，以确保对这些类型的调用成功。

公开定义的 CAS 相关类型从 WPF 程序集移出并移动到 CoreFX 程序集中。 WPF 程序集具有类型转发设置为移动类型的新位置。

| 源程序集 | 目标程序集 | 类型                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *系统.安全.权限.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *系统.安全.权限.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *系统.Windows.扩展.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> 为了尽量减少移植摩擦，在类型中保留了存储和检索与以下属性相关的信息的功能`XamlAccessLevel`。
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>后续步骤

- [了解如何将 .NET 框架 WPF 应用移植到 .NET 核心。](convert-project-from-net-framework.md)
