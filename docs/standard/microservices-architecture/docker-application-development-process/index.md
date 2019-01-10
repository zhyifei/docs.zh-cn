---
title: 基于 Docker 的应用程序的开发流程
description: 获取开发基于 Docker 应用程序的选项的高级概述。 使用所选的 Visual Studio for Windows、Visual Studio for Mac 或 Visual Studio Code 获得多平台支持（Windows、Mac 和 Linux）。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/27/2018
ms.openlocfilehash: eb87f9a214dbffe71dae1e1739f2563c08fac280
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084922"
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="04422-104">基于 Docker 的应用程序的开发流程</span><span class="sxs-lookup"><span data-stu-id="04422-104">Development Process for Docker-Based Applications</span></span>

<span data-ttu-id="04422-105">用你喜欢的方式开发容器化 .NET 应用程序：主要使用 IDE，可辅以 Visual Studio 和 Visual Studio tools for Docker，；主要使用 CLI/编辑器，可辅以 Docker CLI 和 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="04422-105">*Develop containerized .NET applications the way you like, either IDE focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="04422-106">Docker 应用的开发环境</span><span class="sxs-lookup"><span data-stu-id="04422-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="04422-107">开发工具选择：IDE 或编辑器</span><span class="sxs-lookup"><span data-stu-id="04422-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="04422-108">无论你更青睐内容丰富、功能强大的 IDE 还是轻量、灵活的级编辑器，Microsoft 都可为你提供用于开发 Docker 应用程序的工具。</span><span class="sxs-lookup"><span data-stu-id="04422-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="04422-109">**Visual Studio（适用于 Windows）。**</span><span class="sxs-lookup"><span data-stu-id="04422-109">**Visual Studio (for Windows).**</span></span> <span data-ttu-id="04422-110">在使用 Visual Studio 开发基于 Docker 的应用程序时，建议使用已内置的适用于 Docker 的工具随附的 Visual Studio 2017 15.7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="04422-110">When developing Docker-based applications with Visual Studio, it's recommended to use Visual Studio 2017 version 15.7 or later, that comes with tools for Docker already built-in.</span></span> <span data-ttu-id="04422-111">通过适用于 Docker 的工具，可以在目标 Docker 环境中开发、运行和验证应用程序。</span><span class="sxs-lookup"><span data-stu-id="04422-111">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="04422-112">可以按 F5，直接在 Docker 主机中运行并调试应用程序（单个容器或多个容器），也可以按 Ctrl+F5，编辑并刷新应用程序，而无需重新生成该容器。</span><span class="sxs-lookup"><span data-stu-id="04422-112">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="04422-113">要开发基于 Docker 的应用，这是功能最强大的选择。</span><span class="sxs-lookup"><span data-stu-id="04422-113">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="04422-114">**Visual Studio for Mac。**</span><span class="sxs-lookup"><span data-stu-id="04422-114">**Visual Studio for Mac.**</span></span> <span data-ttu-id="04422-115">它是一个 IDE，由 Xamarin Studio 演化而来，在 macOS 中运行，从 2017 年下半年开始可支持 Docker。</span><span class="sxs-lookup"><span data-stu-id="04422-115">It's an IDE, evolution of Xamarin Studio, running in macOS and supports Docker since mid-2017.</span></span> <span data-ttu-id="04422-116">对于使用 Mac 计算机工作而又希望使用功能强大的 IDE 的开发者而言，这应当是理想之选。</span><span class="sxs-lookup"><span data-stu-id="04422-116">This should be the preferred choice for developers working in Mac machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="04422-117">**Visual Studio Code 和 Docker CLI**。</span><span class="sxs-lookup"><span data-stu-id="04422-117">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="04422-118">如果更青睐支持任何开发语言的轻量级跨平台编辑器，可以使用 Microsoft Visual Studio Code (VS Code) 和 Docker CLI。</span><span class="sxs-lookup"><span data-stu-id="04422-118">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Microsoft Visual Studio Code (VS Code) and the Docker CLI.</span></span> <span data-ttu-id="04422-119">这是针对 Mac、Linux 和 Windows 的跨平台开发方法。</span><span class="sxs-lookup"><span data-stu-id="04422-119">This is a cross-platform development approach for Mac, Linux, and Windows.</span></span> <span data-ttu-id="04422-120">此外，Visual Studio Code 还支持 Docker 扩展（例如适用于 Dockerfile 的 IntelliSense）和在编辑器中运行 Docker 命令的快捷任务。</span><span class="sxs-lookup"><span data-stu-id="04422-120">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

<span data-ttu-id="04422-121">安装 [Docker 社区版 (CE)](https://www.docker.com/community-edition) 工具，可以使用单个 Docker CLI 生成适用于 Windows 和 Linux 的应用。</span><span class="sxs-lookup"><span data-stu-id="04422-121">By installing [Docker Community Edition (CE)](https://www.docker.com/community-edition) tools, you can use a single Docker CLI to build apps for both Windows and Linux.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="04422-122">其他资源</span><span class="sxs-lookup"><span data-stu-id="04422-122">Additional resources</span></span>

- <span data-ttu-id="04422-123">**Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="04422-123">**Visual Studio**.</span></span> <span data-ttu-id="04422-124">官方网站。</span><span class="sxs-lookup"><span data-stu-id="04422-124">Official site.</span></span> \
  [*https://visualstudio.microsoft.com/vs/*](https://visualstudio.microsoft.com/vs/)

- <span data-ttu-id="04422-125">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="04422-125">**Visual Studio Code**.</span></span> <span data-ttu-id="04422-126">官方网站。</span><span class="sxs-lookup"><span data-stu-id="04422-126">Official site.</span></span> \
  [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

- <span data-ttu-id="04422-127">**适用于 Mac 和 Windows 的 Docker 社区版 (CE)** \\</span><span class="sxs-lookup"><span data-stu-id="04422-127">**Docker Community Edition (CE) for Mac and Windows** \\</span></span>
  [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="04422-128">适用于 Docker 容器的 .NET 语言和框架</span><span class="sxs-lookup"><span data-stu-id="04422-128">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="04422-129">如本指南的前面几节所述，开发 Docker 容器化 .NET 应用程序时，可以使用 .NET Framework、.NET Core 或开放源 Mono 项目。</span><span class="sxs-lookup"><span data-stu-id="04422-129">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="04422-130">面向 Linux 或 Windows 容器时，根据所使用的 .NET 框架，可以用 C\#、F\# 或 Visual Basic 语言进行开发。</span><span class="sxs-lookup"><span data-stu-id="04422-130">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="04422-131">有关 .NET 语言的详细信息，请参阅博客文章 [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/)（.NET 语言策略）。</span><span class="sxs-lookup"><span data-stu-id="04422-131">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="04422-132">[上一页](../architect-microservice-container-applications/using-azure-service-fabric.md)
>[下一页](docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="04422-132">[Previous](../architect-microservice-container-applications/using-azure-service-fabric.md)
[Next](docker-app-development-workflow.md)</span></span>