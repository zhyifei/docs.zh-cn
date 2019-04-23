---
title: Docker 应用的开发环境
description: 初步了解支持 Docker 开发生命周期的最重要的开发工具选项。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767931"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="2f55e-103">Docker 应用的开发环境</span><span class="sxs-lookup"><span data-stu-id="2f55e-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="2f55e-104">开发工具选择：IDE 或编辑器</span><span class="sxs-lookup"><span data-stu-id="2f55e-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="2f55e-105">无论如果更喜欢完整且功能强大的 IDE 或轻巧便捷编辑器，Microsoft 拥有你的需求时涉及到开发 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f55e-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="2f55e-106">Visual Studio Code 和 Docker CLI （适用于 Mac、 Linux 和 Windows 的跨平台工具）</span><span class="sxs-lookup"><span data-stu-id="2f55e-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="2f55e-107">如果你更青睐支持任何开发语言的轻型、 跨平台编辑器，可以使用 Visual Studio Code 和 Docker CLI。</span><span class="sxs-lookup"><span data-stu-id="2f55e-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="2f55e-108">这些产品提供简单而稳定可靠的体验，这很关键的简化开发人员工作流。</span><span class="sxs-lookup"><span data-stu-id="2f55e-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="2f55e-109">通过安装"Docker for Mac"或"Docker 的 Windows"（开发环境），Docker 开发人员可以使用单个 Docker CLI 为 Windows 或 Linux （运行时环境） 构建应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f55e-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="2f55e-110">此外，Visual Studio Code 支持适用于 Dockerfile 和快捷任务以在编辑器中运行 Docker 命令的 IntelliSense 使用的 Docker 扩展。</span><span class="sxs-lookup"><span data-stu-id="2f55e-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
>
> <span data-ttu-id="2f55e-111">若要下载 Visual Studio Code，请转到<https://code.visualstudio.com/download>。</span><span class="sxs-lookup"><span data-stu-id="2f55e-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="2f55e-112">若要下载适用于 Mac 和 Windows 的 Docker，请转到<https://www.docker.com/products/docker>。</span><span class="sxs-lookup"><span data-stu-id="2f55e-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="2f55e-113">Visual Studio 中使用 Docker 工具 （Windows 开发计算机）</span><span class="sxs-lookup"><span data-stu-id="2f55e-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="2f55e-114">我们建议你使用 Visual Studio 2017 （或更高版本） 启用的内置 Docker 工具。</span><span class="sxs-lookup"><span data-stu-id="2f55e-114">We recommend you use Visual Studio 2017 (or later) with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="2f55e-115">使用 Visual Studio 可以开发、 运行和验证应用程序直接在所选的 Docker 环境中。</span><span class="sxs-lookup"><span data-stu-id="2f55e-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="2f55e-116">按 F5 调试应用程序 （单个容器或多个容器） 直接在 Docker 主机时，或按 Ctrl + F5 编辑和刷新应用，而无需重新生成容器。</span><span class="sxs-lookup"><span data-stu-id="2f55e-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="2f55e-117">Windows 开发人员能够创建适用于 Linux 或 Windows 的 Docker 容器的最简单且最强大选择它。</span><span class="sxs-lookup"><span data-stu-id="2f55e-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="2f55e-118">Visual Studio for Mac （Mac 开发计算机）</span><span class="sxs-lookup"><span data-stu-id="2f55e-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="2f55e-119">可以使用[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)开发基于 Docker 的应用程序时。</span><span class="sxs-lookup"><span data-stu-id="2f55e-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="2f55e-120">Visual Studio for Mac 提供更丰富的 IDE 与 Visual Studio Code 相比 for mac。</span><span class="sxs-lookup"><span data-stu-id="2f55e-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="2f55e-121">选择语言和框架</span><span class="sxs-lookup"><span data-stu-id="2f55e-121">Language and framework choices</span></span>

<span data-ttu-id="2f55e-122">你可以开发 Docker 应用程序使用 Microsoft 工具和大多数流行语言。</span><span class="sxs-lookup"><span data-stu-id="2f55e-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="2f55e-123">下面是一个初始的列表，但您并不仅限于它：</span><span class="sxs-lookup"><span data-stu-id="2f55e-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="2f55e-124">.NET Core 和 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2f55e-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="2f55e-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="2f55e-125">Node.js</span></span>
- <span data-ttu-id="2f55e-126">前往</span><span class="sxs-lookup"><span data-stu-id="2f55e-126">Go</span></span>
- <span data-ttu-id="2f55e-127">Java</span><span class="sxs-lookup"><span data-stu-id="2f55e-127">Java</span></span>
- <span data-ttu-id="2f55e-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="2f55e-128">Ruby</span></span>
- <span data-ttu-id="2f55e-129">Python</span><span class="sxs-lookup"><span data-stu-id="2f55e-129">Python</span></span>

<span data-ttu-id="2f55e-130">基本上，您可以使用支持 Docker Linux 或 Windows 中的任何现代语言。</span><span class="sxs-lookup"><span data-stu-id="2f55e-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2f55e-131">[上一页](deploy-azure-kubernetes-service.md)
>[下一页](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2f55e-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
