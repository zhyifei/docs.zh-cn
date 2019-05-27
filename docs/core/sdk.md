---
title: .NET Core SDK 概述
description: 查看有关 .NET Core SDK 的信息，其是一组用于创建 .NET Core 项目的库和工具。
ms.date: 05/13/2019
ms.technology: dotnet-cli
ms.openlocfilehash: f56d7238eaaaa677db38430358ce94890632469e
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959232"
---
# <a name="net-core-sdk-overview"></a><span data-ttu-id="9828a-103">.NET Core SDK 概述</span><span class="sxs-lookup"><span data-stu-id="9828a-103">.NET Core SDK overview</span></span>

<span data-ttu-id="9828a-104">.NET Core 软件开发工具包 (SDK) 是一组库和工具，使开发人员能够创建 .NET Core 应用程序和库。</span><span class="sxs-lookup"><span data-stu-id="9828a-104">.NET Core Software Development Kit (SDK) is a set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="9828a-105">它包含以下用于构建和运行应用程序的组件：</span><span class="sxs-lookup"><span data-stu-id="9828a-105">It contains the following components that are used to build and run applications:</span></span>

- <span data-ttu-id="9828a-106">.NET Core CLI 工具。</span><span class="sxs-lookup"><span data-stu-id="9828a-106">The .NET Core CLI tools.</span></span>
- <span data-ttu-id="9828a-107">.NET Core 库和运行时。</span><span class="sxs-lookup"><span data-stu-id="9828a-107">.NET Core libraries and runtime.</span></span>
- <span data-ttu-id="9828a-108">`dotnet` [驱动程序](/tools/index.md#driver)。</span><span class="sxs-lookup"><span data-stu-id="9828a-108">The `dotnet` [driver](/tools/index.md#driver).</span></span>

## <a name="acquiring-the-net-core-sdk"></a><span data-ttu-id="9828a-109">获取 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="9828a-109">Acquiring the .NET Core SDK</span></span>

<span data-ttu-id="9828a-110">与任何工具一样，首先应将工具安装到计算机上。</span><span class="sxs-lookup"><span data-stu-id="9828a-110">As with any tooling, the first thing is to get the tools to your machine.</span></span> <span data-ttu-id="9828a-111">根据场景，可以使用以下某个方法安装 SDK：</span><span class="sxs-lookup"><span data-stu-id="9828a-111">Depending on your scenario, you can install the SDK using one of the following methods:</span></span>

- <span data-ttu-id="9828a-112">使用本机安装程序。</span><span class="sxs-lookup"><span data-stu-id="9828a-112">Use the native installers.</span></span>
- <span data-ttu-id="9828a-113">使用安装 shell 脚本。</span><span class="sxs-lookup"><span data-stu-id="9828a-113">Use the installation shell script.</span></span>

<span data-ttu-id="9828a-114">本机安装程序主要用于开发人员的计算机。</span><span class="sxs-lookup"><span data-stu-id="9828a-114">The native installers are primarily meant for developer's machines.</span></span> <span data-ttu-id="9828a-115">SDK 通过每个受支持平台的本机安装机制进行分发，例如 Ubuntu 上的 DEB 包或 Windows 上的 MSI 程序包。</span><span class="sxs-lookup"><span data-stu-id="9828a-115">The SDK is distributed using each supported platform's native install mechanism, such as DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="9828a-116">这些安装程序将根据需要为用户安装并设置环境，以便在安装完成后可立即使用 SDK。</span><span class="sxs-lookup"><span data-stu-id="9828a-116">These installers install and set up the environment as needed for the user to use the SDK immediately after the install.</span></span> <span data-ttu-id="9828a-117">但是，这些安装程序也需要对计算机的管理权限。</span><span class="sxs-lookup"><span data-stu-id="9828a-117">However, they also require administrative privileges on the machine.</span></span> <span data-ttu-id="9828a-118">可以在 [.NET 下载](https://dotnet.microsoft.com/download)页面上找到要安装的 SDK。</span><span class="sxs-lookup"><span data-stu-id="9828a-118">You can find the SDK to install on the [.NET downloads](https://dotnet.microsoft.com/download) page.</span></span>

<span data-ttu-id="9828a-119">另一方面，安装脚本不需要使用管理权限。</span><span class="sxs-lookup"><span data-stu-id="9828a-119">Install scripts, on the other hand, don't require administrative privileges.</span></span> <span data-ttu-id="9828a-120">但是，它们也不会在计算机上安装任何系统必备组件；需要手动安装所有系统必备组件。</span><span class="sxs-lookup"><span data-stu-id="9828a-120">However, they also don't install any prerequisites on the machine; you need to install all of the prerequisites manually.</span></span> <span data-ttu-id="9828a-121">这些脚本主要用于设置生成服务器或希望安装工具但没有管理权限的情况（请务必注意上述系统必备组件注意事项）。</span><span class="sxs-lookup"><span data-stu-id="9828a-121">The scripts are meant mostly for setting up build servers or when you wish to install the tools without admin privileges (do note the prerequisites caveat above).</span></span> <span data-ttu-id="9828a-122">可以在[安装脚本引用](tools/dotnet-install-script.md)一文中找到详细信息。</span><span class="sxs-lookup"><span data-stu-id="9828a-122">You can find more information in the [install script reference](tools/dotnet-install-script.md) article.</span></span> <span data-ttu-id="9828a-123">如果对如何在 CI 构建服务器上设置 SDK 感兴趣，请参阅[在持续集成 (CI) 中使用 .NET Core SDK 和工具](tools/using-ci-with-cli.md)一文。</span><span class="sxs-lookup"><span data-stu-id="9828a-123">If you're interested in how to set up the SDK on your CI build server, see the [Using .NET Core SDK and tools in Continuous Integration (CI)](tools/using-ci-with-cli.md) article.</span></span>

<span data-ttu-id="9828a-124">默认情况下，SDK 以“并排”(SxS) 方式安装，这意味着 CLI 工具的多个版本可以随时在一台计算机上共存。</span><span class="sxs-lookup"><span data-stu-id="9828a-124">By default, the SDK installs in a "side-by-side" (SxS) manner, which means multiple versions of the CLI tools can coexist at any given time on a single machine.</span></span> <span data-ttu-id="9828a-125">[选择要使用的 .NET Core 版本](/versions/selection.md)一文中详细说明了如何在运行 CLI 命令时选择版本。</span><span class="sxs-lookup"><span data-stu-id="9828a-125">How the version gets picked when you're running CLI commands is explained in more detail in the [Select the .NET Core version to use](/versions/selection.md) article.</span></span>

## <a name="see-also"></a><span data-ttu-id="9828a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="9828a-126">See also</span></span>

- [<span data-ttu-id="9828a-127">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="9828a-127">.NET Core CLI</span></span>](tools/index.md)
- [<span data-ttu-id="9828a-128">.NET Core 版本控制概述</span><span class="sxs-lookup"><span data-stu-id="9828a-128">.NET Core versioning overview</span></span>](/versions/index.md)
- [<span data-ttu-id="9828a-129">如何删除 .NET Core 运行时和 SDK</span><span class="sxs-lookup"><span data-stu-id="9828a-129">How to remove the .NET Core runtime and SDK</span></span>](versions/remove-runtime-sdk-versions.md)
- [<span data-ttu-id="9828a-130">选择要使用的 .NET Core 版本</span><span class="sxs-lookup"><span data-stu-id="9828a-130">Select the .NET Core version to use</span></span>](/versions/selection.md)
