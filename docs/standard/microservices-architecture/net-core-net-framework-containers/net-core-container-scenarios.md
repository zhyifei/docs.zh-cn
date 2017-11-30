---
title: "何时选择 Docker 容器中的.NET 核心"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |何时选择 Docker 容器中的.NET 核心"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7e2322bab7937c41d4659fefef11c8937d5eae7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>何时选择 Docker 容器中的.NET 核心

.NET 核心的模块化和轻型性质使特别适合于容器。 当你部署并启动容器时，其映像是比使用.NET Framework 的.NET 核心与最小。 与此相反，若要为某个容器中使用.NET Framework，你必须将你的映像基于 Windows Server Core 映像，这是大量多于 Windows Nano Server 或用于.NET 核心的 Linux 映像。

此外，.NET 核心是跨平台，以便你可以将部署使用 Linux 或 Windows 容器映像的服务器应用程序。 但是，如果你使用传统的.NET Framework，你仅可以部署基于 Windows Server Core 的映像。

以下是为何要选择.NET 核心的更多详细的说明。

## <a name="developing-and-deploying-cross-platform"></a>开发和部署跨平台

很明显，如果你的目标是能够可以运行多个平台支持的 Docker （Linux 和 Windows） 正确的选择的应用程序 （web 应用程序或服务） 是.NET 核心，因为.NET Framework 仅支持 Windows。

.NET 核心还支持 macOS，作为开发平台。 但是，在容器部署到 Docker 主机时，该主机必须 （当前） 基于 Linux 或 Windows。 例如，在开发环境中，你可以使用在 mac 上运行的 Linux 虚拟机

[Visual Studio](https://www.visualstudio.com/)为 Windows 提供的集成的开发环境 (IDE)，并且支持 Docker 开发。 

[Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)是一个 IDE，Xamarin Studio 中，在 macOS 中运行的变化情况并自 2017 中旬支持 Docker。

你还可以使用[Visual Studio Code](https://code.visualstudio.com/) (VS Code) 上 macOS、 Linux 和 Windows。 VS Code 完全支持.NET 核心，包括 IntelliSense 和调试。 由于 VS Code 是轻量的编辑器，可以使用它来开发具有 Docker CLI 结合使用 Mac 上的容器化应用程序和[.NET 核心命令行界面 (CLI) 工具](https://docs.microsoft.com/dotnet/core/tools/?tabs=netcore2x)。 你还可以针对.NET Core 的 Sublime Text、 Emacs、 vi，等的开源 OmniSharp 项目，它为.NET 语言提供 IntelliSense 支持的最第三方编辑器。 除了 Ide 和编辑器中，你可用于所有支持的平台的.NET 核心 CLI。

## <a name="using-containers-for-new-green-field-projects"></a>为新的 （"绿色的字段"） 项目中使用容器

结合使用微服务体系结构中，通常使用容器，尽管它们还可以用来化 web 应用或遵循任何体系结构模式的服务。 你可以使用.NET Framework 上 Windows 容器，但模块性并.NET 核心的轻型性质使其适合容器和微服务体系结构。 当你创建和部署一个容器时，其映像是比使用.NET Framework 的.NET 核心与最小。

## <a name="creating-and-deploying-microservices-on-containers"></a>创建和部署微服务容器

你无法使用传统的.NET Framework 使用纯进程生成基于微服务 （不含容器） 的应用程序。 这样一来，因为.NET Framework 已安装并在进程，之间共享进程浅和快速启动。 但是，如果你使用的容器，传统的.NET Framework 的映像也基于 Windows Server Core，可将它太繁重的微服务上容器方法。

与此相反，.NET 核心是最佳的预发布版本，如果你使用基于容器，面向微服务的系统，因为.NET 核心是轻量。 此外，其相关的容器映像，Linux 映像或 Windows Nano 映像中，是精益和小型使容器 light 和快速启动。

Microservice 要作为越小越好： light 时正常运转，以具有内存占用较小，以具有小限定上下文，以便表示较小的区域问题，从而能够启动和停止快速。 有关这些要求，你将想要使用小和快速实例容器图像，例如.NET Core 容器映像。

微服务体系结构还可以跨服务边界混合技术。 这样，在其他微服务或服务使用 Node.js、 Python、 Java、 GoLang 或其他技术开发的一起工作的新微服务的逐步迁移到.NET 核心。

## <a name="deploying-high-density-in-scalable-systems"></a>在可缩放的系统中部署高的密度

当你基于容器的系统需求的最佳可能密度，粒度和性能时，.NET Core 和 ASP.NET Core 将是你的最佳选择。 ASP.NET 核心是比在传统的.NET Framework 中，ASP.NET 最多十次更快，它又产生微服务，如 Java servlet、 转到和 Node.js 其他常用的行业技术。

这一点尤为重要微服务体系结构，可能有数百个微服务 （容器） 运行的位置。 使用 ASP.NET Core 映像 （基于.NET Core 运行时） 在 Linux 或 Windows Nano 上，你可以运行你的系统以较低数字的服务器或 Vm，最终保存在基础结构的成本和承载。


>[!div class="step-by-step"]
[以前](常规-guidance.md) [下一步] (net-framework 的容器-scenarios.md)
