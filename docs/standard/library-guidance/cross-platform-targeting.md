---
title: 跨平台目标
description: 有关创建跨平台.NET 库的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 72fa891d5b1054af485a98d89b4efb11d6b0018b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374880"
---
# <a name="cross-platform-targeting"></a>跨平台目标

新式.NET 支持多个操作系统和设备。 无论它们是在构建 ASP.NET 网站托管在 Azure 中或.NET 游戏在 Unity 中的.NET 开放源代码库来支持尽可能多的开发人员至关重要。

## <a name="net-standard"></a>.NET Standard

.NET standard 是将跨平台支持添加到.NET 库的最佳方式。 [.NET standard](../net-standard.md)是一种规范的所有.NET 实现可用的.NET Api。 面向.NET Standard，可以生成约束使用的.NET Standard，这意味着可以使用实现该版本的.NET Standard 的所有平台的给定版本中的 Api 的库。

![.NET 标准](./media/cross-platform-targeting/platforms-netstandard.png ".NET 标准")

定目标到.NET Standard，并已成功编译你的项目，并不能保证库将在所有平台上成功运行：

1. 特定于平台的 Api 将在其他平台上失败。 例如，<xref:Microsoft.Win32.Registry?displayProperty=nameWithType>将在 Windows 上成功并引发<xref:System.PlatformNotSupportedException>任何其他操作系统上使用时。
2. Api 的行为可能有所不同。 例如，反射 Api 都具有不同的性能特征时应用程序使用 iOS 或 UWP 预的实时编译。

> [!TIP]
> .NET 团队[提供了 Roslyn 分析器](../analyzers/api-analyzer.md)来帮助您发现可能存在的问题。

**执行 ✔️**开头包括`netstandard2.0`目标。

> 最常规用途库不应需要之外.NET Standard 2.0 的 Api。 .NET standard 2.0 支持的所有新式平台，支持多个平台使用一个目标的建议的方法。

**请避免 ❌**包括`netstandard1.x`目标。

> .NET standard 1.x 分布式为一组精细的 NuGet 包，将创建大型包依赖项关系图并导致生成时下载的包大量的开发人员。 新式.NET 平台，包括.NET Framework 4.6.1、 UWP 和 Xamarin，所有支持.NET Standard 2.0。 您应仅面向.NET Standard 1.x 如果需要专门面向较旧的平台。

**执行 ✔️**包括`netstandard2.0`如果需要面向`netstandard1.x`目标。

> 将使用所有平台支持.NET Standard 2.0`netstandard2.0`目标并且受益于具有较小的包关系图，而较旧的平台仍将起作用并回退为使用`netstandard1.x`目标。

**不这样做 ❌**包括.NET Standard 目标，如果库依赖于特定于平台的应用程序模型。

> 例如，UWP 控件工具包库依赖于才可在 UWP 上的应用程序模型。 特定于应用模型 Api 不会使用.NET Standard 中可用。

## <a name="multi-targeting"></a>多目标

有时您需要从库中访问特定于框架的 Api。 若要调用特定于框架的 Api 的最佳方法使用多目标，这对于许多生成你的项目[.NET 目标框架](../frameworks.md)而不是仅为其中一个。

若要屏蔽使用者无需为单个框架构建，您应该努力拥有.NET 标准输出以及一个或多个特定于框架的输出。 利用多重目标的所有程序集被打包到一个 NuGet 包内。 然后，使用者可以引用同一个包，NuGet 将选择相应的实现。 .NET Standard 库可用作回退库使用无处不在但其中将 NuGet 包提供特定于框架的实现情况除外。 多目标，可在代码中使用条件编译，并调用特定于框架的 Api。

![具有多个程序集的 NuGet 包](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "具有多个程序集的 NuGet 包")

**请考虑 ✔️**面向除了.NET Standard 的.NET 实现。

> 面向.NET 实现可以调用外部.NET Standard 的特定于平台的 Api。
>
> 执行此操作时不删除对.NET Standard 的支持。 相反，引发的实现，提供功能的 Api。 这样一来，你的库可以在任意位置，并支持运行时启动的功能。

**请避免 ❌**使用面向多个与.NET Standard，如果你的源代码的所有目标相同。

> .NET 标准的程序集将自动供 NuGet。 面向单个.NET 实现会增加`*.nupkg`大小无任何好处。

**请考虑 ✔️**添加的目标`net461`时，您能够提供`netstandard2.0`目标。 

> 使用.NET Framework 中的.NET Standard 2.0 已在.NET Framework 4.7.2 中已解决一些问题。 可以改进仍在使用.NET Framework 4.6.1-4.7.1 通过为其提供专为.NET Framework 4.6.1 的二进制文件的开发人员的体验。

**✔️ 执行**分发你的库使用 NuGet 包。

> NuGet 将为开发人员选择最佳的目标和防护它们无需选择相应的实现。

**执行 ✔️**使用项目文件的`TargetFrameworks`时面向多个属性。

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

**请考虑 ✔️**使用[MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras)时面向多个 UWP 和 Xamarin 如极大地简化了你的项目文件。

## <a name="older-targets"></a>较旧的目标

.NET 支持.NET Framework 的目标是长时间超出不再常用的平台以及支持的版本。 虽然让您库的工作上无需解决缺少 Api 的多个目标，可以添加大量开销不存在值。 我们相信某些框架，也无法再以目标，值得考虑其范围和限制。

**不这样做 ❌**包括可移植类库 (PCL) 目标。 例如 `portable-net45+win8+wpa81+wp8`。

> .NET standard 是支持跨平台.NET 库的最新方法，并替换 Pcl。

**不这样做 ❌**包括不再受支持的.NET 平台的目标。 例如：`SL4`、`WP`。

>[!div class="step-by-step"]
[上一页](./get-started.md)
[下一页](./strong-naming.md)
