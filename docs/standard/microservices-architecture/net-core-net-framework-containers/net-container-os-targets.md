---
title: ".NET 容器定向到何种操作系统"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |.NET 容器定向到何种操作系统"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="f756d-104">.NET 容器定向到何种操作系统</span><span class="sxs-lookup"><span data-stu-id="f756d-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="f756d-105">给定的各种操作系统支持 Docker 和.NET Framework 和.NET 核心之间的差异，应针对特定操作系统和具体取决于你使用的 framework 的特定版本。</span><span class="sxs-lookup"><span data-stu-id="f756d-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="f756d-106">对于 Windows，你可以使用 Windows Server Core 或 Windows Nano Server。</span><span class="sxs-lookup"><span data-stu-id="f756d-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="f756d-107">这些 Windows 版本提供不同的特征 (中而不是自承载的 web 服务器，例如，Kestrel Nano Server 中的 Windows Server Core IIS) 程序可能需要的.NET Framework 或.NET Core 分别。</span><span class="sxs-lookup"><span data-stu-id="f756d-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="f756d-108">对于 Linux，多个发行版的可用性和支持中 （如 Debian) 的正式.NET Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="f756d-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="f756d-109">图 3-1 中可以看到的可能的操作系统版本，具体取决于使用的.NET framework。</span><span class="sxs-lookup"><span data-stu-id="f756d-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="f756d-110">**图 3-1。**</span><span class="sxs-lookup"><span data-stu-id="f756d-110">**Figure 3-1.**</span></span> <span data-ttu-id="f756d-111">具体取决于版本的.NET framework 面向的操作系统</span><span class="sxs-lookup"><span data-stu-id="f756d-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="f756d-112">你想要使用不同的 Linux 发行版或要用使用不由 Microsoft 提供的版本映像，你还可以在情况下创建你自己的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="f756d-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="f756d-113">例如，你可能会与传统的.NET Framework 和是 Docker 不常见方案的 Windows Server Core 上运行的 ASP.NET 核心创建映像。</span><span class="sxs-lookup"><span data-stu-id="f756d-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="f756d-114">当映像名称添加到 Dockerfile 文件时，可以选择的操作系统和版本，具体取决于你使用，如以下示例所示的标记：</span><span class="sxs-lookup"><span data-stu-id="f756d-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="f756d-115">microsoft /**dotnet:2.0.0-运行时的 jessie**</span><span class="sxs-lookup"><span data-stu-id="f756d-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="f756d-116">microsoft /**dotnet:2.0.0-运行时的 nanoserver-1709年**</span><span class="sxs-lookup"><span data-stu-id="f756d-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="f756d-117">microsoft /**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="f756d-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="f756d-118">[以前](容器-framework-选择-factors.md) [下一步] (官方-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="f756d-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
