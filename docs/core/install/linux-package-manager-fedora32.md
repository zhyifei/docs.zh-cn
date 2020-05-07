---
title: 在 Fedora 32 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 Fedora 32 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624950"
---
# <a name="fedora-32-package-manager---install-net-core"></a><span data-ttu-id="800f6-103">Fedora 32 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="800f6-103">Fedora 32 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="800f6-104">本文介绍如何使用包管理器在 Fedora 32 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="800f6-104">This article describes how to use a package manager to install .NET Core on Fedora 32.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

<span data-ttu-id="800f6-105">从 Fedora 32 开始，.NET Core 3.1 在 Fedora 的默认包存储库中提供。</span><span class="sxs-lookup"><span data-stu-id="800f6-105">Starting with Fedora 32, .NET Core 3.1 is available in the default package repositories in Fedora.</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="800f6-106">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="800f6-106">Install the .NET Core SDK</span></span>

<span data-ttu-id="800f6-107">安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="800f6-107">Install the .NET Core SDK.</span></span> <span data-ttu-id="800f6-108">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="800f6-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="800f6-109">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="800f6-109">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="800f6-110">安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="800f6-110">Install the ASP.NET runtime.</span></span> <span data-ttu-id="800f6-111">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="800f6-111">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="800f6-112">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="800f6-112">Install the .NET Core runtime</span></span>

<span data-ttu-id="800f6-113">安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="800f6-113">Install the .NET Core runtime.</span></span> <span data-ttu-id="800f6-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="800f6-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="800f6-115">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="800f6-115">How to install other versions</span></span>

<span data-ttu-id="800f6-116">若要安装其他版本的 .NET Core，请手动安装 [.NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) 或 [.NET Core 运行时](runtime.md?pivots=os-linux#download-and-manually-install)。</span><span class="sxs-lookup"><span data-stu-id="800f6-116">To install other versions of .NET Core, manually install [the .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) or [the .NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install).</span></span>
