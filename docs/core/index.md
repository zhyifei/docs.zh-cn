---
title: .NET Core 指南
description: .NET Core 是一种用于创建 Windows、Linux 和 Mac 应用的模块式高性能的 .NET 实现。 了解 .NET Core 以开始使用。
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837007"
---
# <a name="net-core-guide"></a><span data-ttu-id="63c34-104">.NET Core 指南</span><span class="sxs-lookup"><span data-stu-id="63c34-104">.NET Core Guide</span></span>

<span data-ttu-id="63c34-105">[.NET Core](about.md) 是[开放源代码](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)通用开发平台，由 Microsoft 和 .NET 社区在 [GitHub](https://github.com/dotnet/core) 上共同维护。</span><span class="sxs-lookup"><span data-stu-id="63c34-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="63c34-106">它跨平台（支持 Windows、macOS 和 Linux），并且可用于生成设备、云和 IoT 应用程序。</span><span class="sxs-lookup"><span data-stu-id="63c34-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="63c34-107">请参阅[关于 .NET Core](about.md)，详细了解 .NET Core，包括它的特征、支持的语言和框架以及关键 API。</span><span class="sxs-lookup"><span data-stu-id="63c34-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="63c34-108">请学习 [.NET Core 教程](tutorials/index.md)，了解如何创建简单的 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="63c34-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="63c34-109">只需几分钟即可生成并运行第一个应用。</span><span class="sxs-lookup"><span data-stu-id="63c34-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="63c34-110">若要尝试在浏览器中使用 .NET Core，请参阅 [C# 中的数字](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)在线教程。</span><span class="sxs-lookup"><span data-stu-id="63c34-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="63c34-111">下载 .NET Core</span><span class="sxs-lookup"><span data-stu-id="63c34-111">Download .NET Core</span></span>

<span data-ttu-id="63c34-112">下载 [.NET Core SDK](https://www.microsoft.com/net/download)，以尝试在 Windows、macOS 或 Linux 计算机上使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="63c34-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="63c34-113">如果首选使用 Docker 容器，请访问 [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/)。</span><span class="sxs-lookup"><span data-stu-id="63c34-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="63c34-114">若要使用其他版本 .NET Core，可以在 [.NET Core 下载内容](https://dotnet.microsoft.com/download/dotnet-core)中找到所有版本 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="63c34-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="63c34-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="63c34-115">.NET Core 3.1</span></span>

<span data-ttu-id="63c34-116">最新版是 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="63c34-116">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="63c34-117">其中包含对 .NET Core 3.0 的细微改进。</span><span class="sxs-lookup"><span data-stu-id="63c34-117">Which includes minor improvements over .NET Core 3.0.</span></span> <span data-ttu-id="63c34-118">不过，.NET Core 3.1 是一个长期受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="63c34-118">However, .NET Core 3.1 is a long-term supported release.</span></span> <span data-ttu-id="63c34-119">有关 .NET Core 3.1 版本的详细信息，请参阅 [.NET Core 3.1 的新增功能](./whats-new/dotnet-core-3-1.md)。</span><span class="sxs-lookup"><span data-stu-id="63c34-119">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="63c34-120">创建首个应用程序</span><span class="sxs-lookup"><span data-stu-id="63c34-120">Create your first application</span></span>

<span data-ttu-id="63c34-121">安装 .NET Core SDK 后，打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="63c34-121">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="63c34-122">键入以下 `dotnet` 命令以创建并运行 C# 应用程序：</span><span class="sxs-lookup"><span data-stu-id="63c34-122">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="63c34-123">您应看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="63c34-123">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="63c34-124">支持</span><span class="sxs-lookup"><span data-stu-id="63c34-124">Support</span></span>

<span data-ttu-id="63c34-125">[Microsoft 支持](https://dotnet.microsoft.com/platform/support/policy)在 Windows、macOS 和 Linux 上使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="63c34-125">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="63c34-126">它每年会进行多次安全和质量更新（通常每月一次）。</span><span class="sxs-lookup"><span data-stu-id="63c34-126">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="63c34-127">.NET Core 二进制发行版是在 Azure 中的 Microsoft 维护服务器上进行生成和测试，并像其他任何 Microsoft 产品一样获得支持。</span><span class="sxs-lookup"><span data-stu-id="63c34-127">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="63c34-128">[Red Hat 支持在 Red Hat Enterprise Linux (RHEL) 上使用 .NET Core](http://redhatloves.net/)。</span><span class="sxs-lookup"><span data-stu-id="63c34-128">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="63c34-129">Red Hat 从源中生成 .NET Core，并在 [Red Hat 软件集合](https://developers.redhat.com/products/softwarecollections/overview/)中提供它。</span><span class="sxs-lookup"><span data-stu-id="63c34-129">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="63c34-130">Red Hat 和 Microsoft 开展协作，共同确保 .NET Core 能够在 RHEL 上正常运行。</span><span class="sxs-lookup"><span data-stu-id="63c34-130">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
