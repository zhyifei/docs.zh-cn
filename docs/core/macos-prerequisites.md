---
title: "Mac 上 .NET Core 的先决条件"
description: "在 macOS 计算机上开发、部署和运行 .NET Core 应用程序所支持的 macOS 版本和 .NET Core 依赖项。"
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 07/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8feaee2cbfa55e23bd49c0ab76d995f15be343b4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a><span data-ttu-id="59f3f-104">Mac 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="59f3f-104">Prerequisites for .NET Core on Mac</span></span>

<span data-ttu-id="59f3f-105">本文介绍了在 macOS 计算机上开发、部署和运行 .NET Core 应用程序所需的受支持的 macOS 版本和 .NET Core 依赖项。</span><span class="sxs-lookup"><span data-stu-id="59f3f-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="59f3f-106">支持的操作系统版本和随附的依赖项适用于在 Mac 上开发 .NET Core 应用的三种方法：[结合使用常用编辑器和命令行](tutorials/using-with-xplat-cli.md)、[Visual Studio Code](https://code.visualstudio.com/) 和 [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)。</span><span class="sxs-lookup"><span data-stu-id="59f3f-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="59f3f-107">支持的 macOS 版本</span><span class="sxs-lookup"><span data-stu-id="59f3f-107">Supported macOS versions</span></span>

<span data-ttu-id="59f3f-108">以下 macOS 版本均支持 .NET Core：</span><span class="sxs-lookup"><span data-stu-id="59f3f-108">.NET Core is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="59f3f-109">macOS 10.12“Sierra”</span><span class="sxs-lookup"><span data-stu-id="59f3f-109">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="59f3f-110">macOS 10.11“El Capitan”（仅支持 .NET Core 1.x）</span><span class="sxs-lookup"><span data-stu-id="59f3f-110">macOS 10.11 "El Capitan" (.NET Core 1.x only)</span></span>

<span data-ttu-id="59f3f-111">在[支持的操作系统版本](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions)中查看受支持的操作系统的完整列表。</span><span class="sxs-lookup"><span data-stu-id="59f3f-111">See [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) for the complete list of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="59f3f-112">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="59f3f-112">.NET Core dependencies</span></span>

<span data-ttu-id="59f3f-113">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="59f3f-113">**.NET Core 1.x**</span></span>

<span data-ttu-id="59f3f-114">在 macOS 上运行时，.NET Core 1.x 需要 OpenSSL。</span><span class="sxs-lookup"><span data-stu-id="59f3f-114">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="59f3f-115">获取 OpenSSL 的一个简单方法是使用适用于 macOS 的 [Homebrew (“brew”)](https://brew.sh/) 包。</span><span class="sxs-lookup"><span data-stu-id="59f3f-115">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="59f3f-116">在安装 *brew* 后，通过在终端（命令）提示符处执行以下命令来安装 OpenSSL：</span><span class="sxs-lookup"><span data-stu-id="59f3f-116">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="59f3f-117">从 [.NET 下载](https://www.microsoft.com/net/download/core)下载并安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="59f3f-117">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="59f3f-118">如果在 macOS 上安装时遇到问题，请查阅 [1.0.0 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)和 [1.0.1 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)主题。</span><span class="sxs-lookup"><span data-stu-id="59f3f-118">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

<span data-ttu-id="59f3f-119">**.NET Core 2.x**</span><span class="sxs-lookup"><span data-stu-id="59f3f-119">**.NET Core 2.x**</span></span>

<span data-ttu-id="59f3f-120">从 [.NET 下载](https://www.microsoft.com/net/download/core)下载并安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="59f3f-120">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="59f3f-121">如果在 macOS 上安装时遇到问题，请查阅适用于已安装的版本的[已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.0)主题。</span><span class="sxs-lookup"><span data-stu-id="59f3f-121">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="59f3f-122">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="59f3f-122">Visual Studio for Mac</span></span>

<span data-ttu-id="59f3f-123">可以使用任何编辑器，通过 .NET Core SDK 开发 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f3f-123">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="59f3f-124">但是，若要在集成的开发环境中的 Mac 上开发 .NET Core 应用程序，可以使用 [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)。</span><span class="sxs-lookup"><span data-stu-id="59f3f-124">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="59f3f-125">使用 Visual Studio for Mac 在 macOS 上进行 .NET Core 开发需要：</span><span class="sxs-lookup"><span data-stu-id="59f3f-125">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="59f3f-126">macOS 操作系统的受支持版本</span><span class="sxs-lookup"><span data-stu-id="59f3f-126">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="59f3f-127">OpenSSL（仅 .NET Core 1.x；.NET Core 2.x 使用 macOS 上本机可用的安全服务）</span><span class="sxs-lookup"><span data-stu-id="59f3f-127">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="59f3f-128">.NET Core SDK for Mac</span><span class="sxs-lookup"><span data-stu-id="59f3f-128">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="59f3f-129">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="59f3f-129">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

