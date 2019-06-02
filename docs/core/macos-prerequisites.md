---
title: Mac 上 .NET Core 的先决条件
description: 在 macOS 计算机上开发、部署和运行 .NET Core 应用程序所支持的 macOS 版本和 .NET Core 依赖项。
author: mairaw
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 12/14/2018
ms.openlocfilehash: 57346eb5cfdcc9f51c3aab173ed575067b124150
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66299985"
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="d63cd-103">macOS 上 .NET Core 的先决条件</span><span class="sxs-lookup"><span data-stu-id="d63cd-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="d63cd-104">本文介绍了在 macOS 计算机上开发、部署和运行 .NET Core 应用程序所需的受支持的 macOS 版本和 .NET Core 依赖项。</span><span class="sxs-lookup"><span data-stu-id="d63cd-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="d63cd-105">支持的操作系统版本和随附的依赖项适用于在 Mac 上开发 .NET Core 应用的三种方法：[结合使用常用编辑器和命令行](tutorials/using-with-xplat-cli.md)、[Visual Studio Code](https://code.visualstudio.com/) 和 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="d63cd-106">支持的 macOS 版本</span><span class="sxs-lookup"><span data-stu-id="d63cd-106">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d63cd-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d63cd-107">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d63cd-108">以下 macOS 版本支持 .NET Core 2.x：</span><span class="sxs-lookup"><span data-stu-id="d63cd-108">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="d63cd-109">macOS 10.12“Sierra”及更高版本</span><span class="sxs-lookup"><span data-stu-id="d63cd-109">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="d63cd-110">有关 .NET Core 2.1 和 .NET Core 2.2 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)和 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-110">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="d63cd-111">有关下载链接和详细信息，请参阅 [.NET Core 2.2 下载](https://www.microsoft.com/net/download/dotnet-core/2.2)或 [.NET Core 2.1 下载](https://www.microsoft.com/net/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-111">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d63cd-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d63cd-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d63cd-113">以下 macOS 版本支持 .NET Core 1.x：</span><span class="sxs-lookup"><span data-stu-id="d63cd-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="d63cd-114">macOS 10.12“Sierra”</span><span class="sxs-lookup"><span data-stu-id="d63cd-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="d63cd-115">macOS 10.11“El Capitan”</span><span class="sxs-lookup"><span data-stu-id="d63cd-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="d63cd-116">有关 .NET Core 1.1 和 .NET Core 1.0 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 1.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md)和 [.NET Core 1.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-116">See [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) and [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.1 and .NET Core 1.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="d63cd-117">有关下载链接和详细信息，请参阅 [.NET Core 1.1 下载](https://www.microsoft.com/net/download/dotnet-core/1.1)或 [.NET Core 1.0 下载](https://www.microsoft.com/net/download/dotnet-core/1.0)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-117">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="d63cd-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d63cd-118">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d63cd-119">以下 macOS 版本支持 .NET Core 3.0 预览版 3：</span><span class="sxs-lookup"><span data-stu-id="d63cd-119">.NET Core 3.0 Preview 3 is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="d63cd-120">macOS 10.12“Sierra”及更高版本</span><span class="sxs-lookup"><span data-stu-id="d63cd-120">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="d63cd-121">有关 .NET Core 3.0 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-121">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="d63cd-122">有关下载链接和详细信息，请参阅 [.NET Core 3.0 下载](https://www.microsoft.com/net/download/dotnet-core/3.0)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-122">For download links and more information, see [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0).</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="d63cd-123">.NET Core 依赖项</span><span class="sxs-lookup"><span data-stu-id="d63cd-123">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d63cd-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d63cd-124">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d63cd-125">从 [.NET 下载](https://www.microsoft.com/net/download/core)下载并安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="d63cd-125">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d63cd-126">如果在 macOS 上安装时遇到问题，请查阅适用于已安装的版本的[已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.1)主题。</span><span class="sxs-lookup"><span data-stu-id="d63cd-126">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d63cd-127">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d63cd-127">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d63cd-128">在 macOS 上运行时，.NET Core 1.x 需要 OpenSSL。</span><span class="sxs-lookup"><span data-stu-id="d63cd-128">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="d63cd-129">获取 OpenSSL 的一个简单方法是使用适用于 macOS 的 [Homebrew (“brew”)](https://brew.sh/) 包。</span><span class="sxs-lookup"><span data-stu-id="d63cd-129">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="d63cd-130">在安装 *brew* 后，通过在终端（命令）提示符处执行以下命令来安装 OpenSSL：</span><span class="sxs-lookup"><span data-stu-id="d63cd-130">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="d63cd-131">从 [.NET 下载](https://www.microsoft.com/net/download/core)下载并安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="d63cd-131">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d63cd-132">如果在 macOS 上安装时遇到问题，请查阅 [1.0.0 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)和 [1.0.1 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d63cd-132">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="d63cd-133">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d63cd-133">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d63cd-134">从 [.NET 下载](https://www.microsoft.com/net/download/core)下载并安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="d63cd-134">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="d63cd-135">如果在 macOS 上进行安装时遇到问题，请查阅[发行说明](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)主题以了解所安装的版本。</span><span class="sxs-lookup"><span data-stu-id="d63cd-135">If you have problems with the installation on macOS, consult the [Release notes](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) topic for the version you have installed.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="d63cd-136">提高开放文件上限（低于 .NET Core SDK 2.0.2 的 .NET Core 版本）</span><span class="sxs-lookup"><span data-stu-id="d63cd-136">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span>

<span data-ttu-id="d63cd-137">在低于 .NET Core SDK 2.0.2 的旧版 .NET Core 中，macOS 上的默认开放文件上限可能对某些 .NET Core 工作负荷（如还原项目或运行单元测试）不够用。</span><span class="sxs-lookup"><span data-stu-id="d63cd-137">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="d63cd-138">可通过执行以下步骤来增大此限制：</span><span class="sxs-lookup"><span data-stu-id="d63cd-138">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="d63cd-139">使用文本编辑器创建新文件 _/Library/LaunchDaemons/limit.maxfiles.plist_，并在文件中保存以下内容：</span><span class="sxs-lookup"><span data-stu-id="d63cd-139">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
      <dict>
        <key>Label</key>
        <string>limit.maxfiles</string>
        <key>ProgramArguments</key>
        <array>
          <string>launchctl</string>
          <string>limit</string>
          <string>maxfiles</string>
          <string>2048</string>
          <string>4096</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>ServiceIPC</key>
        <false/>
      </dict>
    </plist>
    ```

2. <span data-ttu-id="d63cd-140">在终端窗口中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d63cd-140">In a terminal window, run the following command:</span></span>

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. <span data-ttu-id="d63cd-141">需要重启 Mac 才能应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="d63cd-141">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="d63cd-142">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="d63cd-142">Visual Studio for Mac</span></span>

<span data-ttu-id="d63cd-143">可以使用任何编辑器，通过 .NET Core SDK 开发 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d63cd-143">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="d63cd-144">但是，若要在集成的开发环境中的 Mac 上开发 .NET Core 应用程序，可以使用 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)。</span><span class="sxs-lookup"><span data-stu-id="d63cd-144">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

<span data-ttu-id="d63cd-145">使用 Visual Studio for Mac 在 macOS 上进行 .NET Core 开发需要：</span><span class="sxs-lookup"><span data-stu-id="d63cd-145">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="d63cd-146">macOS 操作系统的受支持版本</span><span class="sxs-lookup"><span data-stu-id="d63cd-146">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="d63cd-147">OpenSSL（仅 .NET Core 1.x；.NET Core 2.x 使用 macOS 上本机可用的安全服务）</span><span class="sxs-lookup"><span data-stu-id="d63cd-147">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="d63cd-148">.NET Core SDK for Mac</span><span class="sxs-lookup"><span data-stu-id="d63cd-148">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="d63cd-149">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="d63cd-149">Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
