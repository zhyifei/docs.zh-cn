---
title: 使用 .NET 容器时定位的操作系统
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 .NET 容器时定位的操作系统
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 9e1d07e48d88376efb5fbdbdadc999c8dcd5082d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374903"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="2ea3a-103">使用 .NET 容器时定位的操作系统</span><span class="sxs-lookup"><span data-stu-id="2ea3a-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="2ea3a-104">由于 Docker 支持多种操作系统，且鉴于 .NET Framework 和 .NET Core 之间的差异，应根据所使用的框架，面向特定操作系统和特定版本。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="2ea3a-105">对于 Windows，可使用 Windows Server Core 或 Windows Nano Server。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="2ea3a-106">这两种 Windows 版本分别提供 .NET Framework 和 .NET Core 各自所需的特征（Windows Server Core 中的 IIS 与 Nano Server 中自承载的 web 服务器，如 Kestrel）。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="2ea3a-107">对于 Linux，正式的 .NET Docker 映像（如 Debian）中提供并支持多个发行版本。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="2ea3a-108">图 3-1 显示基于所使用的 .NET framework，可使用的操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![部署旧的 .NET Framework 应用程序时，必须以与旧应用程序和 IIS 兼容且具有更大映像的 Windows Server Core 为目标。](./media/image1.png)

<span data-ttu-id="2ea3a-113">**图 3-1。**</span><span class="sxs-lookup"><span data-stu-id="2ea3a-113">**Figure 3-1.**</span></span> <span data-ttu-id="2ea3a-114">根据 .NET framework 确定要面向的操作系统</span><span class="sxs-lookup"><span data-stu-id="2ea3a-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="2ea3a-115">如果想使用不同的 Linux 发行版本或要使用 Microsoft 不支持的映像版本，还可以创建自己的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="2ea3a-116">例如，可以使用 ASP.NET Core 创建一个在传统 .NET Framework 和 Windows Server Core 上运行的映像，但这不是常见的 Docker 方案。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="2ea3a-117">将映像名称添加到 Dockerfile 文件后，可根据所使用的标记选择操作系统和版本，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="2ea3a-117">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2ea3a-118">图像</span><span class="sxs-lookup"><span data-stu-id="2ea3a-118">Image</span></span></th>
<th><span data-ttu-id="2ea3a-119">注释</span><span class="sxs-lookup"><span data-stu-id="2ea3a-119">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2ea3a-120">microsoft/dotnet:2.2-runtime</span><span class="sxs-lookup"><span data-stu-id="2ea3a-120">microsoft/dotnet:2.2-runtime</span></span></td>
<td><span data-ttu-id="2ea3a-121">.NET Core 2.2 多体系结构：支持 Linux 和 Windows Nano Server，具体取决于 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-121">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2ea3a-122">microsoft/dotnet:2.2-aspnetcore-runtime</span><span class="sxs-lookup"><span data-stu-id="2ea3a-122">microsoft/dotnet:2.2-aspnetcore-runtime</span></span></td>
<td><p><span data-ttu-id="2ea3a-123">ASP.NET Core 2.2 多体系结构：支持 Linux 和 Windows Nano Server，具体取决于 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-123">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></p>
<p><span data-ttu-id="2ea3a-124">ASP.NET Core 的 aspnetcore 映像具有多个优化。</span><span class="sxs-lookup"><span data-stu-id="2ea3a-124">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2ea3a-125">microsoft/dotnet:2.2-aspnetcore-runtime-alpine</span><span class="sxs-lookup"><span data-stu-id="2ea3a-125">microsoft/dotnet:2.2-aspnetcore-runtime-alpine</span></span></td>
<td><span data-ttu-id="2ea3a-126">Linux Alpine 发行版上的 .NET Core 2.2 仅运行时</span><span class="sxs-lookup"><span data-stu-id="2ea3a-126">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2ea3a-127">microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="2ea3a-127">microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1803</span></span></td>
<td><span data-ttu-id="2ea3a-128">Windows Nano Server（Windows Server 版本 1803）上的 .NET Core 2.2 仅运行时</span><span class="sxs-lookup"><span data-stu-id="2ea3a-128">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span></td>
</tr>
</tbody>
</table>

> [!div class="step-by-step"]
> <span data-ttu-id="2ea3a-129">[上一页](container-framework-choice-factors.md)
> [下一页](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="2ea3a-129">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>