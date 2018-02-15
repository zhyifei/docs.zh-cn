---
title: "Docker 应用的开发环境"
description: "使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ad1a6e4cb0974ebb067cf1a7be987d696e8bc82a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="68910-104">Docker 应用的开发环境</span><span class="sxs-lookup"><span data-stu-id="68910-104">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="68910-105">开发工具的选择： IDE 或编辑器</span><span class="sxs-lookup"><span data-stu-id="68910-105">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="68910-106">不管如果你愿意完整且功能强大的 IDE 或轻量，并灵活编辑器，Microsoft 将使你在覆盖时涉及到开发 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="68910-106">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="68910-107">Visual Studio Code 和 Docker CLI （于 Mac、 Linux 和 Windows 的跨平台工具）</span><span class="sxs-lookup"><span data-stu-id="68910-107">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="68910-108">如果需要支持任何开发语言的轻量、 跨平台编辑器，你可以使用 Visual Studio Code 和 Docker CLI。</span><span class="sxs-lookup"><span data-stu-id="68910-108">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="68910-109">这些产品提供简单而稳定可靠体验，这很关键的简化开发人员工作流。</span><span class="sxs-lookup"><span data-stu-id="68910-109">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="68910-110">通过安装"Docker 的 Mac"或"用于 Windows 的 Docker"（开发环境），Docker 开发人员可以使用单个 Docker CLI 生成适用于 Windows 或 Linux （运行时环境） 应用。</span><span class="sxs-lookup"><span data-stu-id="68910-110">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="68910-111">此外，Visual Studio Code 支持 IntelliSense Dockerfile 和快捷任务运行 Docker 命令在编辑器中使用 Docker 扩展。</span><span class="sxs-lookup"><span data-stu-id="68910-111">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="68910-112">若要下载 Visual Studio 代码，请转到<https://code.visualstudio.com/download>。</span><span class="sxs-lookup"><span data-stu-id="68910-112">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="68910-113">若要下载适用于 Mac 和 Windows 的 Docker，请转到<http://www.docker.com/products/docker>。</span><span class="sxs-lookup"><span data-stu-id="68910-113">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="68910-114">使用 Docker 工具的 visual Studio</span><span class="sxs-lookup"><span data-stu-id="68910-114">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="68910-115">在你使用 Visual Studio 2015 时你可以安装外接程序工具"Visual Studio Docker 的工具"。</span><span class="sxs-lookup"><span data-stu-id="68910-115">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="68910-116">为 Visual Studio 2017，Docker 工具来自内置已。</span><span class="sxs-lookup"><span data-stu-id="68910-116">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="68910-117">你可以开发两种情况下，运行，并验证你的应用程序直接在选 Docker 环境中。</span><span class="sxs-lookup"><span data-stu-id="68910-117">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="68910-118">F5 你的应用程序 （单个容器或多个容器） 直接在 Docker 主机进行调试，或按 Ctrl + F5 来编辑，并刷新应用程序，而无需重新生成容器。</span><span class="sxs-lookup"><span data-stu-id="68910-118">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="68910-119">这是 Windows 开发人员为 Linux 或 Windows 创建 Docker 容器的最简单、 更强大选择。</span><span class="sxs-lookup"><span data-stu-id="68910-119">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="68910-120">若要下载 Visual Studio Docker 工具，请转到<https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>。</span><span class="sxs-lookup"><span data-stu-id="68910-120">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="68910-121">语言和框架选项</span><span class="sxs-lookup"><span data-stu-id="68910-121">Language and framework choices</span></span>

<span data-ttu-id="68910-122">你可以开发 Docker 应用程序和与大多数现代语言的 Microsoft 工具。</span><span class="sxs-lookup"><span data-stu-id="68910-122">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="68910-123">下面是一个初始的列表，但并不局限于它：</span><span class="sxs-lookup"><span data-stu-id="68910-123">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="68910-124">.NET core 和 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68910-124">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="68910-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="68910-125">Node.js</span></span>

-   <span data-ttu-id="68910-126">Golang</span><span class="sxs-lookup"><span data-stu-id="68910-126">Golang</span></span>

-   <span data-ttu-id="68910-127">Java</span><span class="sxs-lookup"><span data-stu-id="68910-127">Java</span></span>

-   <span data-ttu-id="68910-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="68910-128">Ruby</span></span>

-   <span data-ttu-id="68910-129">Python</span><span class="sxs-lookup"><span data-stu-id="68910-129">Python</span></span>

<span data-ttu-id="68910-130">基本上，你可以使用支持的 Linux 或 Windows 中的 Docker 任何现代语言。</span><span class="sxs-lookup"><span data-stu-id="68910-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="68910-131">[以前](安排-高的可伸缩性-availability.md) [下一步] (docker-应用程序的内部的循环-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="68910-131">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
