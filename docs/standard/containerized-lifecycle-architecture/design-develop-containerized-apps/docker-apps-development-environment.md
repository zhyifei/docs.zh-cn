---
title: Docker 应用的开发环境
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 8db9f37e4fa8df63060982857d457c9e1ce90f60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="d34e7-103">Docker 应用的开发环境</span><span class="sxs-lookup"><span data-stu-id="d34e7-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="d34e7-104">开发工具选择：IDE 或编辑器</span><span class="sxs-lookup"><span data-stu-id="d34e7-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="d34e7-105">不管如果你愿意完整且功能强大的 IDE 或轻量，并灵活编辑器，Microsoft 将使你在覆盖时涉及到开发 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d34e7-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="d34e7-106">Visual Studio Code 和 Docker CLI （于 Mac、 Linux 和 Windows 的跨平台工具）</span><span class="sxs-lookup"><span data-stu-id="d34e7-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="d34e7-107">如果需要支持任何开发语言的轻量、 跨平台编辑器，你可以使用 Visual Studio Code 和 Docker CLI。</span><span class="sxs-lookup"><span data-stu-id="d34e7-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="d34e7-108">这些产品提供简单而稳定可靠体验，这很关键的简化开发人员工作流。</span><span class="sxs-lookup"><span data-stu-id="d34e7-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="d34e7-109">通过安装"Docker 的 Mac"或"用于 Windows 的 Docker"（开发环境），Docker 开发人员可以使用单个 Docker CLI 生成适用于 Windows 或 Linux （运行时环境） 应用。</span><span class="sxs-lookup"><span data-stu-id="d34e7-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="d34e7-110">此外，Visual Studio Code 支持 IntelliSense Dockerfile 和快捷任务运行 Docker 命令在编辑器中使用 Docker 扩展。</span><span class="sxs-lookup"><span data-stu-id="d34e7-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="d34e7-111">若要下载 Visual Studio 代码，请转到<https://code.visualstudio.com/download>。</span><span class="sxs-lookup"><span data-stu-id="d34e7-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="d34e7-112">若要下载适用于 Mac 和 Windows 的 Docker，请转到<http://www.docker.com/products/docker>。</span><span class="sxs-lookup"><span data-stu-id="d34e7-112">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="d34e7-113">使用 Docker 工具的 visual Studio</span><span class="sxs-lookup"><span data-stu-id="d34e7-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="d34e7-114">在你使用 Visual Studio 2015 时你可以安装外接程序工具"Visual Studio Docker 的工具"。</span><span class="sxs-lookup"><span data-stu-id="d34e7-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="d34e7-115">为 Visual Studio 2017，Docker 工具来自内置已。</span><span class="sxs-lookup"><span data-stu-id="d34e7-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="d34e7-116">你可以开发两种情况下，运行，并验证你的应用程序直接在选 Docker 环境中。</span><span class="sxs-lookup"><span data-stu-id="d34e7-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="d34e7-117">F5 你的应用程序 （单个容器或多个容器） 直接在 Docker 主机进行调试，或按 Ctrl + F5 来编辑，并刷新应用程序，而无需重新生成容器。</span><span class="sxs-lookup"><span data-stu-id="d34e7-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="d34e7-118">这是 Windows 开发人员为 Linux 或 Windows 创建 Docker 容器的最简单、 更强大选择。</span><span class="sxs-lookup"><span data-stu-id="d34e7-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="d34e7-119">若要下载 Visual Studio Docker 工具，请转到<https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>。</span><span class="sxs-lookup"><span data-stu-id="d34e7-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="d34e7-120">语言和框架选项</span><span class="sxs-lookup"><span data-stu-id="d34e7-120">Language and framework choices</span></span>

<span data-ttu-id="d34e7-121">你可以开发 Docker 应用程序和与大多数现代语言的 Microsoft 工具。</span><span class="sxs-lookup"><span data-stu-id="d34e7-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="d34e7-122">下面是一个初始的列表，但并不局限于它：</span><span class="sxs-lookup"><span data-stu-id="d34e7-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="d34e7-123">.NET core 和 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d34e7-123">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="d34e7-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="d34e7-124">Node.js</span></span>

-   <span data-ttu-id="d34e7-125">Golang</span><span class="sxs-lookup"><span data-stu-id="d34e7-125">Golang</span></span>

-   <span data-ttu-id="d34e7-126">Java</span><span class="sxs-lookup"><span data-stu-id="d34e7-126">Java</span></span>

-   <span data-ttu-id="d34e7-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="d34e7-127">Ruby</span></span>

-   <span data-ttu-id="d34e7-128">Python</span><span class="sxs-lookup"><span data-stu-id="d34e7-128">Python</span></span>

<span data-ttu-id="d34e7-129">基本上，你可以使用支持的 Linux 或 Windows 中的 Docker 任何现代语言。</span><span class="sxs-lookup"><span data-stu-id="d34e7-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d34e7-130">[以前] (orchestrate-high-scalability-availability.md) [下一步] (docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d34e7-130">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
