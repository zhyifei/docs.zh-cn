---
title: 面向 Azure .NET 和 .NET Core 开发人员的工具
description: 获取工具以通过 Windows、Linux 和 Mac 环境开始使用 Azure .NET 库。
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433162"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a>面向 .NET 和 .NET Core Azure 开发人员的工具

## <a name="sdk-downloads"></a>SDK 下载

.NET 的 Azure 库作为[NuGet 包](https://www.nuget.org/packages?q=windowsazureofficial)实现。 有关 Azure 服务组织的安装说明，请参阅[API 参考](/dotnet/api/overview/azure/?view=azure-dotnet)。

## <a name="development-tools"></a>开发工具

Visual Studio 具有用于内置许多 Azure 服务的工具。 某些 Azure 服务具有其他可用工具或仿真器，如[Azure 存储资源管理器](https://azure.microsoft.com/features/storage-explorer/)。 如有必要，请参阅 Azure 服务的文档，了解任何其他工具。

这些说明为您的操作系统安装建议的启动开发环境。

## <a name="windows"></a>[Windows](#tab/windows)

Visual Studio 版本 2017 及更高版本已内置支持 Azure 开发。 以下步骤描述了在可视化工作室中启用 Azure 开发支持。

对于 Visual Studio 2015 及更早版本，<a href="vs2015-install.md">请按照以下说明操作</a>。

### <a name="step-1-download-visual-studio-2019"></a>第 1 步：下载视觉工作室 2019

如果您已经安装了 Visual Studio 2019，则可以跳过此步骤。

> [!div class="nextstepaction"]
> [下载 Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>步骤 2：安装两个 Azure 工作负荷

在可视化工作室安装程序中，安装可视化工作室（或修改现有安装）。 确保选择了*Azure*开发和*ASP.NET和 Web 开发*工作负荷。

### <a name="step-3-develop-with-net-on-azure"></a>步骤 3：在 Azure 上使用 .NET 进行开发

首先，[在 Azure 应用服务中部署第一个 ASP.NET Core Web 应用](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet)。

## <a name="macos"></a>[macOS](#tab/macos)

Visual Studio for Mac 提供所需的一切功能用于进行 Azure 开发。

### <a name="step-1-download-visual-studio-for-mac"></a>步骤 1：下载 Visual Studio for Mac

> [!div class="nextstepaction"]
> [下载 Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

在安装过程中，默认情况下选择 Azure 工具。

## <a name="linux"></a>[Linux](#tab/linux)

Visual Studio Code 提供所需的一切功能让你在 Linux 上进行 Azure 开发。

### <a name="step-1-download-the-net-core-sdk"></a>步骤 1：下载 .NET Core SDK

用于 .NET Core 应用的 SDK 和命令行工具。

> [!div class="nextstepaction"]
> [下载 .NET Core SDK](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>步骤 2：Visual Studio Code

在任何操作系统上编辑和调试 .NET Core 应用：Windows、Mac 和 Linux。

> [!div class="nextstepaction"]
> [下载 Visual Studio Code](https://code.visualstudio.com)

---
