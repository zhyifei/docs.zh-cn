---
title: ".NET Core SDK 概述"
description: "查看有关 .NET Core SDK 的信息，其是一组用于创建 .NET Core 项目的库和工具。"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 26bc9822-e42b-48ec-b0d6-499dc604add7
ms.openlocfilehash: 8f3d0f5b3bccdd1ca25fa1202c2c727e402fe668
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-sdk-overview"></a><span data-ttu-id="314c2-104">.NET Core SDK 概述</span><span class="sxs-lookup"><span data-stu-id="314c2-104">.NET Core SDK Overview</span></span> 

## <a name="introduction"></a><span data-ttu-id="314c2-105">介绍</span><span class="sxs-lookup"><span data-stu-id="314c2-105">Introduction</span></span>
<span data-ttu-id="314c2-106">.NET Core 软件开发工具包 (SDK) 是一组库和工具，使开发人员能够创建 .NET Core 应用程序和库。</span><span class="sxs-lookup"><span data-stu-id="314c2-106">.NET Core Software Development Kit (SDK) is a set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="314c2-107">这是开发人员最可能获取的包。</span><span class="sxs-lookup"><span data-stu-id="314c2-107">This is the package that developers will most likely acquire.</span></span> 

<span data-ttu-id="314c2-108">它包含下列组件：</span><span class="sxs-lookup"><span data-stu-id="314c2-108">It contains the following components:</span></span>

1. <span data-ttu-id="314c2-109">.NET Core 命令行工具，用于生成应用程序</span><span class="sxs-lookup"><span data-stu-id="314c2-109">The .NET Core Command Line Tools that are used to build applications</span></span>
2. <span data-ttu-id="314c2-110">.NET Core（库和运行时），用于生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="314c2-110">.NET Core (libraries and runtime) that allow applications to both be built and run</span></span>
3. <span data-ttu-id="314c2-111">`dotnet` 驱动程序，用于运行 [CLI 命令](tools/index.md)和应用程序</span><span class="sxs-lookup"><span data-stu-id="314c2-111">The `dotnet` driver for running the [CLI commands](tools/index.md) as well as running applications</span></span>


## <a name="acquiring-the-net-core-sdk"></a><span data-ttu-id="314c2-112">获取 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="314c2-112">Acquiring the .NET Core SDK</span></span>
<span data-ttu-id="314c2-113">与任何工具一样，首先应将工具安装到计算机上。</span><span class="sxs-lookup"><span data-stu-id="314c2-113">As with any tooling, the first thing is to get the tools to your machine.</span></span> <span data-ttu-id="314c2-114">根据具体情况，可以使用本机安装程序安装 SDK 或使用 shell 脚本安装。</span><span class="sxs-lookup"><span data-stu-id="314c2-114">Depending on your scenario, you can either use the native installers to install the SDK or use the installation shell script.</span></span>

<span data-ttu-id="314c2-115">本机安装程序主要用于开发人员的计算机。</span><span class="sxs-lookup"><span data-stu-id="314c2-115">The native installers are primarily meant for developer's machines.</span></span> <span data-ttu-id="314c2-116">可以使用所有受支持的平台的本机安装机制发布 SDK，例如 Ubuntu 上的 DEB 或 Windows 上的 MSI 包。</span><span class="sxs-lookup"><span data-stu-id="314c2-116">The SDK is distributed using each supported platform's native install mechanism, for instance DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="314c2-117">这些安装程序将根据需要为用户安装并设置环境，以便在安装完成后可立即使用 SDK。</span><span class="sxs-lookup"><span data-stu-id="314c2-117">These installers will install and set up the environment as needed for the user to use the SDK immediately after the install.</span></span> <span data-ttu-id="314c2-118">但是，这些安装程序也需要对计算机的管理权限。</span><span class="sxs-lookup"><span data-stu-id="314c2-118">However, they also require administrative privileges on the machine.</span></span> <span data-ttu-id="314c2-119">可以在 [.NET Core 安装指南](https://aka.ms/dotnetcoregs)中查看安装说明。</span><span class="sxs-lookup"><span data-stu-id="314c2-119">You can view the installation instructions on the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>

<span data-ttu-id="314c2-120">另一方面，安装脚本不需要管理权限。</span><span class="sxs-lookup"><span data-stu-id="314c2-120">Install scripts, on the other hand, do not require administrative privileges.</span></span> <span data-ttu-id="314c2-121">但是，它们也不会在计算机上安装任何系统必备组件；需要手动安装所有系统必备组件。</span><span class="sxs-lookup"><span data-stu-id="314c2-121">However, they will also not install any prerequisites on the machine; you need to install all of the prerequisites manually.</span></span> <span data-ttu-id="314c2-122">这些脚本主要用于设置生成服务器或希望安装工具但没有管理权限的情况（请务必注意上述系统必备组件注意事项）。</span><span class="sxs-lookup"><span data-stu-id="314c2-122">The scripts are meant mostly for setting up build servers or when you wish to install the tools without admin privileges (do note the prerequisites caveat above).</span></span> <span data-ttu-id="314c2-123">可以在[安装脚本引用主题](tools/dotnet-install-script.md)中找到详细信息。</span><span class="sxs-lookup"><span data-stu-id="314c2-123">You can find more information on the [install script reference topic](tools/dotnet-install-script.md).</span></span> <span data-ttu-id="314c2-124">如果对如何在 CI 生成服务器上设置 SDK 感兴趣，可以看一看 [CI 服务器的 SDK](tools/using-ci-with-cli.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="314c2-124">If you are interested in how to set up SDK on your CI build server you can take a look at the [SDK with CI servers](tools/using-ci-with-cli.md) document.</span></span> 

<span data-ttu-id="314c2-125">默认情况下，SDK 将以“并行”(SxS) 方式安装。</span><span class="sxs-lookup"><span data-stu-id="314c2-125">By default, the SDK will install in a "side-by-side" (SxS) manner.</span></span> <span data-ttu-id="314c2-126">这意味着多个版本的 CLI 工具在任何给定时间内可在一台计算机上共存。</span><span class="sxs-lookup"><span data-stu-id="314c2-126">This means that multiple versions of the CLI tools can coexist at any given time on a single machine.</span></span> <span data-ttu-id="314c2-127">有关如何使用正确版本的详细信息，请参阅 .NET Core 命令行工具主题中的[驱动程序部分](tools/index.md#driver)。</span><span class="sxs-lookup"><span data-stu-id="314c2-127">How the correct version gets used is explained in more detail in the [driver section](tools/index.md#driver) of .NET Core Command Line Tools topic.</span></span>
