---
title: ".NET Core 分发打包"
description: "了解如何为 .NET Core 打包、命名并进行版本控制以进行分发。"
keywords: ".NET, .NET Core, 源, 生成"
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 71b9d722-c5a8-4271-9ce1-d87e7ae2494d
ms.openlocfilehash: 7ff5ed127ad0d4f435c697a8f35b33c7ba3b56ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-distribution-packaging"></a>.NET Core 分发打包

由于 .NET Core 现已可用于更多平台，因此了解如何为其打包、命名并进行版本控制将很有用。 这样，无论用户选择在哪里运行 .NET，包维护人员均可以帮助确保获得一致的体验。

## <a name="net-core-components"></a>.NET Core 组件

.NET Core 由三个需要打包的主要部分构成：

1. 主机也称为“muxer”）有两个不同角色：激活运行时以启动应用程序，及激活 SDK 以向其分派命令。 主机是本机可执行文件 (`dotnet.exe`)，并是其支持策略库（安装在 `host/fxr` 中）。 它由 [`dotnet/core-setup`](https://github.com/dotnet/core-setup/) 存储库中的代码生成。 通常一个给定计算机上只有一个主机，但这并不是一个严格的要求。
2. 框架由运行时和支持的托管库构成。 可以将框架作为应用程序的一部分进行安装，或者将其作为可供多个应用程序重用的某个中心位置中的共享框架进行安装。 一个给定计算机上可以安装任意数量的共享框架。 共享框架在 `shared/Microsoft.NETCore.App/<version>` 下运行。 主机跨修补程序版本前滚。 如果应用程序面向 `Microsoft.NETCore.App` 1.0.0，但仅存在 1.0.4，则将针对 1.0.4 启动此应用。
3. SDK（也称为“工具”）是一组托管工具，可用于编写和生成 .NET Core 库和应用程序。 SDK 包括 CLI、MSBuild 及相关生成任务和目标、NuGet、新项目模板等。一个计算机上可以拥有多个 SDK（例如，生成显式要求旧版本的项目时），但是建议使用最新发布的工具。

## <a name="recommended-package-names"></a>建议的包名称

下列指南是针对包名称的建议。 包维护人员可以出于各种原因选择从其中分离，例如他们面向的是特定分发版本的不同传统。

### <a name="minimum-package-set"></a>最小包集

* `dotnet-runtime-[major].[minor]`：包含指定版本的共享框架（包管理器中应仅提供针对给定的主要/次要组合的最新修补程序版本）。 **依赖项**：`dotnet-host`
* `dotnet-sdk`：最新的 SDK。 **依赖项**：最新的 `dotnet-sdk-[major].[minor]`。
* `dotnet-sdk-[major].[minor]`：包含指定版本的 SDK。 指定的版本是包含的共享框架中最高的包含版本，以便用户可以将 SDK 轻松关联到共享框架。 **依赖项**： `dotnet-host`，一个或多个 `dotnet-runtime-[major].[minor]`（这些运行时之一将供 SDK 代码本身使用，在此处用户针对其他运行时进行生成和运行）。
* `dotnet-host`：最新的主机。

#### <a name="preview-versions"></a>预览版

包维护人员可以决定包含共享框架和 SDK 的预览版。 未进行版本控制的 `dotnet-sdk` 包中不的包含这些版本，但是可将其发布为已进行版本控制的包，并将额外的预览标记追加到该名称的主要和次要版本中。 例如，可以有 `dotnet-sdk-2.0-preview-final` 包。

### <a name="optional-additional-packages"></a>可选的其他包

一些维护人员可以选择提供其他包，例如：

* `dotnet-lts`：共享框架的最新长期支持 (LTS) 版本。 [LTS 和当前版本系列](~/docs/core/versions/lts-current.md)对应 .NET Core 的不同发布阶段。 用户可以根据他们愿意进行更新的频率来选择采用某一个或其他系列。 此概念也与支持级别绑定，因此它可能有意义，也可能没有意义，具体取决于考虑使用的分发版。

## <a name="disk-layout"></a>磁盘布局

安装 .NET Core 包时，其目标目的地在磁盘上的相对位置。
`dotnet.exe` 主机应位于包含 `dotnet-sdk` SDK 包和 `dotnet-runtime` 共享框架包的已进行版本控制的内容的 `sdk` 和 `shared` 文件夹旁边。

包内的文件和目录的磁盘布局已进行版本控制。 这表示更新到最新的 `dotnet-runtime` 会将新版本与之前的版本并行安装，从而降低了更新包后中断现有应用程序的可能性。 包更新不应删除之前的版本。

## <a name="update-policies"></a>更新策略

执行 `update` 后，各个包的行为如下所示：

* `dotnet-runtime-[major].[minor]`：新的修补程序版本更新此包，但是新的次要和主要版本是独立的包。
* `dotnet-sdk`：`update` 前滚主要、次要和修补程序版本。
* `dotnet-sdk-[major].[minor]`：新的修补程序版本更新此包，但是新的次要和主要版本是独立的包。
* `dotnet-lts`：`update` 前滚主要、次要和修补程序版本。

本主题已介绍了对打包 .NET Core 的建议，但是各个分发版可随意选择提供何种版本及何时提供。 例如，与保持最新相比，更注重稳定性的分发版可以选择仅发布与 LTS 版本系列贴近的版本。