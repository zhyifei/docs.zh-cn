---
title: .NET Core 指南
description: .NET Core 是一种用于创建 Windows、Linux 和 Mac 应用的模块式高性能的 .NET 实现。 了解 .NET Core 以开始使用。
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: cfa7c27871204b808c9d753a970d5abb907a183e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512836"
---
# <a name="net-core-guide"></a><span data-ttu-id="51026-104">.NET Core 指南</span><span class="sxs-lookup"><span data-stu-id="51026-104">.NET Core Guide</span></span>

<span data-ttu-id="51026-105">[.NET Core](about.md) 是[开放源代码](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)通用开发平台，由 Microsoft 和 [GitHub](https://github.com/dotnet/core) 上的 .NET 社区共同维护。</span><span class="sxs-lookup"><span data-stu-id="51026-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="51026-106">它跨平台支持 Windows、macOS 和 Linux，并且可用于设备、云和 IoT 应用程序。</span><span class="sxs-lookup"><span data-stu-id="51026-106">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and IoT applications.</span></span>

<span data-ttu-id="51026-107">请参阅[关于 .NET Core](about.md)，以详细了解 .NET Core，包括它的特征、支持的语言和框架以及密钥 API。</span><span class="sxs-lookup"><span data-stu-id="51026-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="51026-108">请学习 [.NET Core 教程](tutorials/index.md)，了解如何创建简单的 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="51026-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="51026-109">只需几分钟即可生成并运行第一个应用。</span><span class="sxs-lookup"><span data-stu-id="51026-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="51026-110">若要尝试在浏览器中使用 .NET Core，请参阅 [C# 中的数字](https://docs.microsoft.com/dotnet/csharp/quick-starts/hello-world)快速入门。</span><span class="sxs-lookup"><span data-stu-id="51026-110">If you want to try .NET Core in you browser, look at the [Numbers in C#](https://docs.microsoft.com/dotnet/csharp/quick-starts/hello-world) quickstart.</span></span>

## <a name="download-net-core-21"></a><span data-ttu-id="51026-111">下载 .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="51026-111">Download .NET Core 2.1</span></span>

<span data-ttu-id="51026-112">下载 [.NET Core 2.1 SDK](https://www.microsoft.com/net/download)，以尝试在 Windows、macOS 或 Linux 计算机上使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="51026-112">Download the [.NET Core  2.1 SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="51026-113">若要使用 Docker 容器，请访问 [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/)。</span><span class="sxs-lookup"><span data-stu-id="51026-113">Visit [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) if you prefer to use Docker containers.</span></span>

<span data-ttu-id="51026-114">若要使用其他版本 .NET Core，可以在 [.NET Core 下载内容](https://www.microsoft.com/net/download/archives)中找到所有版本 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="51026-114">All .NET Core versions are available at [.NET Core Downloads](https://www.microsoft.com/net/download/archives) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="51026-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="51026-115">.NET Core 2.1</span></span>

<span data-ttu-id="51026-116">最新版是 [.NET Core 2.1](whats-new/dotnet-core-2-1.md)。</span><span class="sxs-lookup"><span data-stu-id="51026-116">The latest version is [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span></span> <span data-ttu-id="51026-117">新功能包括：全局工具、高性能 API（如 <xref:System.Span%601?displayProperty=nameWithType>）、分层 JIT 编译、[生成](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/)和[运行时性能改进](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/)，并支持 Alpine 和 ARM32。</span><span class="sxs-lookup"><span data-stu-id="51026-117">New features include: global tools, high-performance APIs (such as <xref:System.Span%601?displayProperty=nameWithType>), tiered JIT compilation, [build](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and [runtime performance improvements](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/), and support for Alpine and ARM32.</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="51026-118">创建首个应用程序</span><span class="sxs-lookup"><span data-stu-id="51026-118">Create your first application</span></span>

<span data-ttu-id="51026-119">安装 .NET Core SDK 后，打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="51026-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="51026-120">键入以下 `dotnet` 命令以创建并运行 C# 应用程序。</span><span class="sxs-lookup"><span data-stu-id="51026-120">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="51026-121">您应看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="51026-121">You should see the following output:</span></span>

```console
Hello World!
```

## <a name="support"></a><span data-ttu-id="51026-122">支持</span><span class="sxs-lookup"><span data-stu-id="51026-122">Support</span></span>

<span data-ttu-id="51026-123">[Microsoft 支持](https://www.microsoft.com/net/support/policy)在 Windows、macOS 和 Linux 上使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="51026-123">.NET Core is [supported by Microsoft](https://www.microsoft.com/net/support/policy), on Windows, macOS and Linux.</span></span> <span data-ttu-id="51026-124">它每年会进行多次安全和质量更新（通常每月一次）。</span><span class="sxs-lookup"><span data-stu-id="51026-124">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="51026-125">.NET Core 二进制发行版是在 Azure 中的 Microsoft 维护服务器上进行生成和测试，并像其他任何 Microsoft 产品一样获得支持。</span><span class="sxs-lookup"><span data-stu-id="51026-125">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="51026-126">[Red Hat 支持在 Red Hat Enterprise Linux (RHEL) 上使用 .NET Core](http://redhatloves.net/)。</span><span class="sxs-lookup"><span data-stu-id="51026-126">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="51026-127">Red Hat 从源中生成 .NET Core，并在 [Red Hat 软件集合](https://developers.redhat.com/products/softwarecollections/overview/)中提供它。</span><span class="sxs-lookup"><span data-stu-id="51026-127">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="51026-128">Red Hat 和 Microsoft 开展协作，共同确保 .NET Core 能够在 RHEL 上正常运行。</span><span class="sxs-lookup"><span data-stu-id="51026-128">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>