---
title: .NET Core SDK 概述
description: 查看有关 .NET Core SDK 的信息，其是一组用于创建 .NET Core 项目的库和工具。
ms.date: 05/13/2019
ms.technology: dotnet-cli
ms.openlocfilehash: f56d7238eaaaa677db38430358ce94890632469e
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959232"
---
# <a name="net-core-sdk-overview"></a>.NET Core SDK 概述

.NET Core 软件开发工具包 (SDK) 是一组库和工具，使开发人员能够创建 .NET Core 应用程序和库。 它包含以下用于构建和运行应用程序的组件：

- .NET Core CLI 工具。
- .NET Core 库和运行时。
- `dotnet` [驱动程序](/tools/index.md#driver)。

## <a name="acquiring-the-net-core-sdk"></a>获取 .NET Core SDK

与任何工具一样，首先应将工具安装到计算机上。 根据场景，可以使用以下某个方法安装 SDK：

- 使用本机安装程序。
- 使用安装 shell 脚本。

本机安装程序主要用于开发人员的计算机。 SDK 通过每个受支持平台的本机安装机制进行分发，例如 Ubuntu 上的 DEB 包或 Windows 上的 MSI 程序包。 这些安装程序将根据需要为用户安装并设置环境，以便在安装完成后可立即使用 SDK。 但是，这些安装程序也需要对计算机的管理权限。 可以在 [.NET 下载](https://dotnet.microsoft.com/download)页面上找到要安装的 SDK。

另一方面，安装脚本不需要使用管理权限。 但是，它们也不会在计算机上安装任何系统必备组件；需要手动安装所有系统必备组件。 这些脚本主要用于设置生成服务器或希望安装工具但没有管理权限的情况（请务必注意上述系统必备组件注意事项）。 可以在[安装脚本引用](tools/dotnet-install-script.md)一文中找到详细信息。 如果对如何在 CI 构建服务器上设置 SDK 感兴趣，请参阅[在持续集成 (CI) 中使用 .NET Core SDK 和工具](tools/using-ci-with-cli.md)一文。

默认情况下，SDK 以“并排”(SxS) 方式安装，这意味着 CLI 工具的多个版本可以随时在一台计算机上共存。 [选择要使用的 .NET Core 版本](/versions/selection.md)一文中详细说明了如何在运行 CLI 命令时选择版本。

## <a name="see-also"></a>请参阅

- [.NET Core CLI](tools/index.md)
- [.NET Core 版本控制概述](/versions/index.md)
- [如何删除 .NET Core 运行时和 SDK](versions/remove-runtime-sdk-versions.md)
- [选择要使用的 .NET Core 版本](/versions/selection.md)
