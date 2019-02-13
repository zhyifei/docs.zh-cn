---
title: Docker 应用的开发环境
description: 初步了解支持 Docker 开发生命周期的最重要的开发工具选项。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 1d22b45a8eee9198d337df9f0b8b4b78371fa31a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219992"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="e40b3-103">Docker 应用的开发环境</span><span class="sxs-lookup"><span data-stu-id="e40b3-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="e40b3-104">开发工具选择：IDE 或编辑器</span><span class="sxs-lookup"><span data-stu-id="e40b3-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="e40b3-105">无论如果更喜欢完整且功能强大的 IDE 或轻巧便捷编辑器，Microsoft 拥有你的需求时涉及到开发 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e40b3-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="e40b3-106">Visual Studio Code 和 Docker CLI （适用于 Mac、 Linux 和 Windows 的跨平台工具）</span><span class="sxs-lookup"><span data-stu-id="e40b3-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="e40b3-107">如果你更青睐支持任何开发语言的轻型、 跨平台编辑器，可以使用 Visual Studio Code 和 Docker CLI。</span><span class="sxs-lookup"><span data-stu-id="e40b3-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="e40b3-108">这些产品提供简单而稳定可靠的体验，这很关键的简化开发人员工作流。</span><span class="sxs-lookup"><span data-stu-id="e40b3-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="e40b3-109">通过安装"Docker for Mac"或"Docker 的 Windows"（开发环境），Docker 开发人员可以使用单个 Docker CLI 为 Windows 或 Linux （运行时环境） 构建应用程序。</span><span class="sxs-lookup"><span data-stu-id="e40b3-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="e40b3-110">此外，Visual Studio Code 支持适用于 Dockerfile 和快捷任务以在编辑器中运行 Docker 命令的 IntelliSense 使用的 Docker 扩展。</span><span class="sxs-lookup"><span data-stu-id="e40b3-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="e40b3-111">若要下载 Visual Studio Code，请转到<https://code.visualstudio.com/download>。</span><span class="sxs-lookup"><span data-stu-id="e40b3-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="e40b3-112">若要下载适用于 Mac 和 Windows 的 Docker，请转到<https://www.docker.com/products/docker>。</span><span class="sxs-lookup"><span data-stu-id="e40b3-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="e40b3-113">Visual Studio 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="e40b3-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="e40b3-114">当你使用的 Visual Studio 2015 可以安装外接程序工具"Docker Tools for Visual Studio。"</span><span class="sxs-lookup"><span data-stu-id="e40b3-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="e40b3-115">为 Visual Studio 2017 中，Docker 工具会在生成已。</span><span class="sxs-lookup"><span data-stu-id="e40b3-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="e40b3-116">在这两种情况下可以开发、 运行和验证应用程序直接在所选的 Docker 环境中。</span><span class="sxs-lookup"><span data-stu-id="e40b3-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="e40b3-117">F5 直接在 Docker 应用程序 （单个容器或多个容器） 进行调试，托管或按 Ctrl + F5 编辑和刷新应用，而无需重新生成容器。</span><span class="sxs-lookup"><span data-stu-id="e40b3-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="e40b3-118">这是创建适用于 Linux 或 Windows 的 Docker 容器的 Windows 开发人员的最简单、 更强大的选择。</span><span class="sxs-lookup"><span data-stu-id="e40b3-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="e40b3-119">若要下载 Docker Tools for Visual Studio，请转到<https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>。</span><span class="sxs-lookup"><span data-stu-id="e40b3-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="e40b3-120">选择语言和框架</span><span class="sxs-lookup"><span data-stu-id="e40b3-120">Language and framework choices</span></span>

<span data-ttu-id="e40b3-121">你可以开发 Docker 应用程序和大多数流行语言与 Microsoft 工具。</span><span class="sxs-lookup"><span data-stu-id="e40b3-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="e40b3-122">下面是一个初始的列表，但并不局限于它：</span><span class="sxs-lookup"><span data-stu-id="e40b3-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="e40b3-123">.NET Core 和 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e40b3-123">.NET Core and ASP.NET Core</span></span>
-   <span data-ttu-id="e40b3-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="e40b3-124">Node.js</span></span>
-   <span data-ttu-id="e40b3-125">Golang</span><span class="sxs-lookup"><span data-stu-id="e40b3-125">Golang</span></span>
-   <span data-ttu-id="e40b3-126">Java</span><span class="sxs-lookup"><span data-stu-id="e40b3-126">Java</span></span>
-   <span data-ttu-id="e40b3-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="e40b3-127">Ruby</span></span>
-   <span data-ttu-id="e40b3-128">Python</span><span class="sxs-lookup"><span data-stu-id="e40b3-128">Python</span></span>

<span data-ttu-id="e40b3-129">基本上，您可以使用支持 Docker Linux 或 Windows 中的任何现代语言。</span><span class="sxs-lookup"><span data-stu-id="e40b3-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e40b3-130">[上一页](deploy-azure-kubernetes-service.md)
>[下一页](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e40b3-130">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>