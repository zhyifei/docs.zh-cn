---
title: "目标框架 | Microsoft Docs"
description: "介绍了 .NET Core 应用程序和库的目标框架。"
keywords: ".NET, .NET Core, 框架, TFM"
author: richlander
ms.author: mairaw
ms.date: 04/27/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
ms.translationtype: Machine Translation
ms.sourcegitcommit: 45835eb80642253f80ea630ae9db1ac766b72b9c
ms.openlocfilehash: 11c1f11e4f8354b7573d03e680cf4a8a16fa26d9
ms.contentlocale: zh-cn
ms.lasthandoff: 05/11/2017

---

# <a name="target-frameworks"></a>目标框架

*框架*定义了用于创建应用程序和库的对象、方法和工具。 .NET Framework 用于创建主要在运行 Windows 操作系统的系统上执行的应用程序和库。 使用 .NET Core 中的框架，可以生成在各种操作系统上运行的应用程序和库。

鉴于*框架*和*平台*这两个词在短语中的使用方式，有时会将两者混淆。 让解释变得更为困难的是，*平台*这个词在不同的上下文中含义也不同。 例如，你会发现，在生成应用程序和库的上下文中，“.NET Core”被称为“.NET Core 框架”，而在执行应用程序和库代码的上下文中，“.NET Core”则被称为“.NET Core 平台”。 *计算平台*描述了应用程序的运行*位置和方式*。 由于 .NET Core 使用 [.NET Core 公共语言运行时 (CoreCLR)](https://github.com/dotnet/coreclr) 执行代码，因此也是平台。 .NET Framework 亦是如此，它使用[公共语言运行时 (CLR)](clr.md) 执行使用 .NET Framework 框架对象、方法和工具开发的应用程序和库代码。 经常会在文档中看到“跨平台”一词；但当看到这个词时，应将其视为“跨操作系统和跨体系结构（x86、x64、arm）”，因为这就是作者通常要传达的意思。

框架的对象和方法称为应用程序编程接口 (API)。 框架 API 用于 [Visual Studio](https://www.visualstudio.com/)、[Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)、[Visual Studio Code](https://code.visualstudio.com/) 以及其他集成开发环境 (IDE) 和编辑器，从而提供用于开发的一组正确对象和方法。 [NuGet](https://www.nuget.org/) 还将框架用于 NuGet 包的生产和使用目的，以确保对在应用程序或库中定位的框架生产和使用适当的包。

*定位一个或多个框架*时，便已决定要使用哪些 API 集和哪些 API 版本。 框架可通过以下几种方式进行引用：按产品名称、按完整格式或缩写格式的框架名称以及按系列。

## <a name="referring-to-frameworks"></a>引用框架

引用框架的方法有多种，整个 .NET Core 文档使用了其中大部分方法。 以 .NET Framework 4.6.2 为例，可以使用以下格式：

**提到产品**

可以提到 .NET 平台或运行时。 两种格式都同样有效。

* .NET Framework 4.6.2
* .NET 4.6.2

**引用框架**

可以使用 TFM 的完整形式或缩写形式提到框架或框架的目标。 两种格式都同样有效。

* `.NETFramework,Version=4.6.2`
* `net462`

**引用框架系列**

可以使用框架 ID 的完整形式或缩写形式提到框架系列。 两种格式都同样有效。

* `.NETFramework`
* `net`

## <a name="latest-framework-versions"></a>最新框架版本

下表定义了可以使用的一组框架、如何引用这些框架，以及它们实现的 [.NET Standard 库](library.md)版本。 这些框架版本是最新的稳定版本。 预览版不会显示。

| 框架             | 最新版本 | 目标框架名字对象 (TFM) | 精简目标框架名字对象 (TFM) | .NET Standard 版本 | 元包 |
| :-------------------: | :------------: | :----------------------------: | :------------------------------------: | :-------------------: | :---------: |
| .NET Standard         | 1.6.1          | .NETStandard,Version=1.6       | netstandard1.6                         | 不可用                   | [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) |
| .NET Core 应用程序 | 1.1.1          | .NETCoreApp,Version=1.1        | netcoreapp1.1                          | 1.6                   | [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) |
| .NET Framework        | 4.6.2          | .NETFramework,Version=4.6.2    | net462                                 | 1.5                   | 不可用 |

## <a name="supported-frameworks"></a>支持的框架

通常按简短的目标框架名字对象 (*TFM*) 引用框架。 在 .NET Standard 中，这也泛化成 *TxM*，以便一次引用多个框架。 NuGet 客户端支持以下框架。 等效项显示在括号 (`[]`) 内。

| 名称                       | 缩写 | TFM/TxM                                    |
| -------------------------- | ------------ | -------------------------------------------- |
| .NET Standard              | netstandard  | netstandard1.0                               |
|                            |              | netstandard1.1                               |
|                            |              | netstandard1.2                               |
|                            |              | netstandard1.3                               |
|                            |              | netstandard1.4                               |
|                            |              | netstandard1.5                               |
|                            |              | netstandard1.6                               |
| .NET 核心                  | netcoreapp   | netcoreapp1.0                                |
|                            |              | netcoreapp1.1                                |
| .NET Framework             | net          | net11                                        |
|                            |              | net20                                        |
|                            |              | net35                                        |
|                            |              | net40                                        |
|                            |              | net403                                       |
|                            |              | net45                                        |
|                            |              | net451                                       |
|                            |              | net452                                       |
|                            |              | net46                                        |
|                            |              | net461                                       |
|                            |              | net462                                       |
| Windows 应用商店              | netcore      | netcore [netcore45]                          |
|                            |              | netcore45 [win, win8]                        |
|                            |              | netcore451 [win81]                           |
| .NET Micro Framework       | netmf        | netmf                                        |
| Silverlight                | sl           | sl4                                          |
|                            |              | sl5                                          |
| Windows Phone              | wp           | wp [wp7]                                     |
|                            |              | wp7                                          |
|                            |              | wp75                                         |
|                            |              | wp8                                          |
|                            |              | wp81                                         |
|                            |              | wpa81                                        |
| 通用 Windows 平台 | uap          | uap [uap10.0]                                |
|                            |              | uap10.0 [win10] [netcore50]                  |

## <a name="deprecated-frameworks"></a>弃用的框架

以下框架已弃用。 定位这些框架的包应迁移到指明的替代框架。

| 弃用的框架 | Replacement |
| -------------------- | ----------- |
| aspnet50             | netcoreapp  |
| aspnetcore50         |             |
| dnxcore50            |             |
| dnx                  |             |
| dnx45                |             |
| dnx451               |             |
| dnx452               |             |
| dotnet               | netstandard |
| dotnet50             |             |
| dotnet51             |             |
| dotnet52             |             |
| dotnet53             |             |
| dotnet54             |             |
| dotnet55             |             |
| dotnet56             |             |
| netcore50            | uap10.0     |
| win                  | netcore45   |
| win8                 | netcore45   |
| win81                | netcore451  |
| win10                | uap10.0     |
| winrt                | netcore45   |

## <a name="precedence"></a>优先级

许多框架相互关联且彼此兼容，但不一定是等效的：

| 框架                        | 可以使用   |
| -------------------------------- | --------- |
| uap（通用 Windows 平台） | win81     |
|                                  | wpa81     |
|                                  | netcore50 |
| win（Windows 应用商店）              | winrt     |
|                                  | winrt45   |

## <a name="net-standard"></a>.NET Standard

[.NET Standard](https://github.com/dotnet/standard) 简化了二进制兼容框架之间的引用，允许一个目标框架引用其他框架的组合。 有关详细信息，请参阅 [.NET Standard 库](library.md)主题。

[NuGet 工具获取最新的框架工具](http://nugettoolsdev.azurewebsites.net/)模拟了用于从基于项目框架的包中的许多可用框架资产中选择一个框架的 NuGet 逻辑。 若要使用此工具，请输入一个项目框架和一个或多个包框架。 单击“提交”按钮。 此工具会指明你列出的包框架和项目框架是否兼容。

## <a name="portable-class-libraries"></a>可移植类库

若要了解可移植类库，请参阅 NuGet 文档中*目标框架*主题的[可移植类库](https://docs.microsoft.com/nuget/schema/target-frameworks#portable-class-libraries)部分。 Stephen Cleary 创建了一个工具，其中列出了受支持的 PCL。 有关详细信息，请参阅 [.NET 中的框架配置文件](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)。

