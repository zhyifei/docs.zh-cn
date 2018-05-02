---
title: Windows 上 .NET Core 的先决条件
description: 了解在 Windows 计算机上开发和运行 .NET Core 应用程序所需的依赖项。
author: JRAlexander
ms.author: johalex
ms.date: 04/24/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 6f2ba8540a38f8e30d3d968f5e2c891c850053aa
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a>Windows 上 .NET Core 的先决条件

本文介绍了在 Windows 上开发 .NET Core 应用程序所需的依赖项。 支持的 OS 版本和依赖项适用于在 Windows 上开发 .NET Core 应用程序的三种方法：

* [命令行](tutorials/using-with-xplat-cli.md)
* [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a>支持 .NET Core 的 Windows 版本

以下版本支持 .NET Core：

* Windows 7 SP1
* Windows 8.1
* Windows 10 周年更新（版本 1607）或更高版本
* Windows Server 2008 R2 SP1（完全服务器或服务器核心）
* Windows Server 2012 SP1（完全服务器或服务器核心）
* Windows Server 2012 R2（完全服务器或服务器核心）
* Windows Server 2016（完全服务器、服务器核心或 Nano Server）

有关支持 .NET Core 2.x 的操作系统的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。

有关支持 .NET Core 1.x 的操作系统的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。

## <a name="net-core-dependencies"></a>.NET Core 依赖项

在早于 Windows 10 和 Windows Server 2016 的 Windows 版本上运行 .NET Core 1.1 及更低版本时，需要 Visual C++ Redistributable。 .NET Core 安装程序自动安装此依赖项。

如果出现以下情况，必须手动安装 [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)：

* 使用[安装程序脚本](./tools/dotnet-install-script.md)安装 .NET Core。
* 部署独立式 .NET Core 应用程序。
* 从源中生成产品。
* 通过 .zip 文件安装 .NET Core。 这可能包括 build/CI/CD 服务器。

> [!NOTE]
> 对于 Windows 8.1 和更早版本，或 Windows Server 2012 R2 和更早版本：请确保你的 Windows 安装为最新版本，并且包含可以通过 Windows 更新安装的 [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows)。 如果没有安装此更新，则在启动 .NET Core 应用程序时会看到如下错误：`The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`。

## <a name="prerequisites-with-visual-studio-2017"></a>Visual Studio 2017 的先决条件

可以使用任何编辑器，通过 .NET Core SDK 开发 .NET Core 应用程序。 [Visual Studio 2017](#visual-studio-2017) 提供了用于在 Windows 上开发 .NET Core 应用程序的集成开发环境。

在[发行说明](/visualstudio/releasenotes/vs2017-relnotes)中可以详细了解 Visual Studio 2017 中的更改。

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

若要使用 Visual Studio 2017 开发 .NET Core 2.x 应用程序，请执行以下操作：

 1. [下载并安装 Visual Studio 2017 版本 15.3.0 或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs-15-3-workloads.jpg)

安装“.NET Core 跨平台开发”工具集后，Visual Studio 2017 默认使用 .NET Core 1.x。 安装 .NET Core 2.x SDK，以便在 Visual Studio 2017 中获取 .NET Core 2.x 支持。

 2. 获取 [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core)。
 3. 按照下列说明操作，将现有或新的 .NET Core 1.x 项目重定目标到 .NET Core 2.x：
    * 在“项目”菜单上，选择“属性”。
    * 在“目标框架”选择菜单上，将值设置为“.NET Core 2.0”。

![已选择“.NET Core 2.0”目标框架菜单项的 Visual Studio 2017 应用程序项目属性屏幕截图](./media/windows-prerequisites/Targeting-dotnetCore2.png)

安装 .NET Core 2.x SDK 后，Visual Studio 2017 默认使用 .NET Core SDK 2.x，并支持以下操作：

* 打开、生成和运行现有 .NET Core 1.x 项目。
* 将 .NET Core 1.x 项目重定目标到 .NET Core 2.x，再生成并运行。
* 新建 .NET Core 2.x 项目。

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

若要使用 Visual Studio 开发 .NET Core 1.x 应用程序，请[下载并安装 Visual Studio 2017 RTM（版本 15.0.26228.4）或更高版本](/visualstudio/install/install-visual-studio)，并选择“其他工具集”部分中的“.NET Core 跨平台开发”工作负载。

![选中“.NET Core 跨平台开发”工作负荷的 Visual Studio 2017 安装的屏幕截图](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> 可以使用 Visual Studio 2015 进行 .NET Core 1.x 开发，但不建议这么做，原因如下：
  > * .NET Core 工具是预览版，并不受支持。
  > * 项目依据的 project.json 已遭弃用。
>
> 若要详细了解项目格式更改，请参阅[变更的简要概览](./tools/cli-msbuild-architecture.md)。
---

> [!TIP]
> 若要验证 Visual Studio 2017 版本，请执行以下操作：
>
> * 在“帮助”菜单上，选择“关于 Microsoft Visual Studio”。
> * 在“关于 Microsoft Visual Studio”对话框中，验证版本号。
>   * 对于 .NET Core 2.1 Preview 1 应用，Visual Studio 2017 版本应为 15.6 预览版 6 或更高版本。
>   * 对于 .NET Core 2.0 应用，Visual Studio 2017 版本应为 15.3 或更高版本。
>   * 对于 .NET Core 1.x 应用，Visual Studio 2017 版本应为 15.0 或更高版本。
