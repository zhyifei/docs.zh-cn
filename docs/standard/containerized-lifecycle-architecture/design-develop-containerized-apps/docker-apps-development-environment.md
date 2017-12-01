---
title: "Docker 应用的开发环境"
description: "使用 Microsoft 平台和工具的 Docker 容器化应用程序生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: eedba16136ad394bda45cc871944f9b876c8ee38
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2017
---
# <a name="development-environment-for-docker-apps"></a>Docker 应用的开发环境

## <a name="development-tools-choices-ide-or-editor"></a>开发工具的选择： IDE 或编辑器

不管如果你愿意完整且功能强大的 IDE 或轻量，并灵活编辑器，Microsoft 将使你在覆盖时涉及到开发 Docker 应用程序。

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code 和 Docker CLI （于 Mac、 Linux 和 Windows 的跨平台工具）

如果需要支持任何开发语言的轻量、 跨平台编辑器，你可以使用 Visual Studio Code 和 Docker CLI。 这些产品提供简单而稳定可靠体验，这很关键的简化开发人员工作流。 通过安装"Docker 的 Mac"或"用于 Windows 的 Docker"（开发环境），Docker 开发人员可以使用单个 Docker CLI 生成适用于 Windows 或 Linux （运行时环境） 应用。 此外，Visual Studio Code 支持 IntelliSense Dockerfile 和快捷任务运行 Docker 命令在编辑器中使用 Docker 扩展。

> [!NOTE]
> 若要下载 Visual Studio 代码，请转到<https://code.visualstudio.com/download>。

若要下载适用于 Mac 和 Windows 的 Docker，请转到<http://www.docker.com/products/docker>。

### <a name="visual-studio-with-docker-tools"></a>使用 Docker 工具的 visual Studio

在你使用 Visual Studio 2015 时你可以安装外接程序工具"Visual Studio Docker 的工具"。 为 Visual Studio 2017，Docker 工具来自内置已。 你可以开发两种情况下，运行，并验证你的应用程序直接在选 Docker 环境中。 F5 你的应用程序 （单个容器或多个容器） 直接在 Docker 主机进行调试，或按 Ctrl + F5 来编辑，并刷新应用程序，而无需重新生成容器。 这是 Windows 开发人员为 Linux 或 Windows 创建 Docker 容器的最简单、 更强大选择。

> [!NOTE]
> 若要下载 Visual Studio Docker 工具，请转到<https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>。

## <a name="language-and-framework-choices"></a>语言和框架选项

你可以开发 Docker 应用程序和与大多数现代语言的 Microsoft 工具。 下面是一个初始的列表，但并不局限于它：

-   .NET core 和 ASP.NET Core

-   Node.js

-   Golang

-   Java

-   Ruby

-   Python

基本上，你可以使用支持的 Linux 或 Windows 中的 Docker 任何现代语言。


>[!div class="step-by-step"]
[以前](安排-高的可伸缩性-availability.md) [下一步] (docker-应用程序的内部的循环-workflow.md)
