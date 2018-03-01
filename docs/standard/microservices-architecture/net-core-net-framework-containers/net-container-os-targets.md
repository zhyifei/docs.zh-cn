---
title: "使用 .NET 容器时定位的操作系统"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 .NET 容器时定位的操作系统"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ef7a21efa23be3a5181f08066a093abbb915c20f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="44f74-104">使用 .NET 容器时定位的操作系统</span><span class="sxs-lookup"><span data-stu-id="44f74-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="44f74-105">由于 Docker 支持多种操作系统，且鉴于 .NET Framework 和 .NET Core 之间的差异，应根据所使用的框架，面向特定操作系统和特定版本。</span><span class="sxs-lookup"><span data-stu-id="44f74-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="44f74-106">对于 Windows，可使用 Windows Server Core 或 Windows Nano Server。</span><span class="sxs-lookup"><span data-stu-id="44f74-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="44f74-107">这两种 Windows 版本分别提供 .NET Framework 和 .NET Core 各自所需的特征（Windows Server Core 中的 IIS 与 Nano Server 中自承载的 web 服务器，如 Kestrel）。</span><span class="sxs-lookup"><span data-stu-id="44f74-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="44f74-108">对于 Linux，正式的 .NET Docker 映像（如 Debian）中提供并支持多个发行版本。</span><span class="sxs-lookup"><span data-stu-id="44f74-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="44f74-109">图 3-1 显示基于所使用的 .NET framework，可使用的操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="44f74-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="44f74-110">**图 3-1。**</span><span class="sxs-lookup"><span data-stu-id="44f74-110">**Figure 3-1.**</span></span> <span data-ttu-id="44f74-111">根据 .NET framework 确定要面向的操作系统</span><span class="sxs-lookup"><span data-stu-id="44f74-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="44f74-112">如果想使用不同的 Linux 发行版本或要使用 Microsoft 不支持的映像版本，还可以创建自己的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="44f74-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="44f74-113">例如，可以使用 ASP.NET Core 创建一个在传统 .NET Framework 和 Windows Server Core 上运行的映像，但这不是常见的 Docker 方案。</span><span class="sxs-lookup"><span data-stu-id="44f74-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="44f74-114">将映像名称添加到 Dockerfile 文件后，可根据所使用的标记选择操作系统和版本，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="44f74-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="44f74-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span><span class="sxs-lookup"><span data-stu-id="44f74-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="44f74-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="44f74-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="44f74-117">microsoft/**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="44f74-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="44f74-118">[上一项] (container-framework-choice-factors.md) [下一项] (official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="44f74-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
