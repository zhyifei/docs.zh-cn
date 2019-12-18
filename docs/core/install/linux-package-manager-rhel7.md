---
title: 在 Linux RHEL 7 包管理器上安装 .NET Core - .NET Core
description: 使用包管理器在 RHEL 7 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: f17a410ccea1ef4dec32de1d80ef6aac889aa6f3
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998905"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="60353-103">RHEL 7 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="60353-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="60353-104">本文介绍如何使用包管理器在 RHEL 7 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="60353-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="60353-105">对于 RHEL 7，.NET Core 3.1 尚不可用。</span><span class="sxs-lookup"><span data-stu-id="60353-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="60353-106">注册 Red Hat 订阅</span><span class="sxs-lookup"><span data-stu-id="60353-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="60353-107">若要在 RHEL 上从 Red Hat 安装 .NET Core，首先需要使用 Red Hat 订阅管理器进行注册。</span><span class="sxs-lookup"><span data-stu-id="60353-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="60353-108">如果未在系统上完成此操作，或者不确定是否完成了此操作，请参阅[适用于 .NET Core 的 Red Hat 产品文档](https://access.redhat.com/documentation/net_core/)。</span><span class="sxs-lookup"><span data-stu-id="60353-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="60353-109">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="60353-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="60353-110">向订阅管理器注册后，你就可安装并启用 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="60353-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="60353-111">在终端中，运行以下命令以启用并安装 RHEL 7 dotnet 通道。</span><span class="sxs-lookup"><span data-stu-id="60353-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="60353-112">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="60353-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="60353-113">向订阅管理器注册后，你就可安装并启用 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="60353-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="60353-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="60353-114">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="60353-115">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="60353-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="60353-116">向订阅管理器注册后，你就可安装并启用 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="60353-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="60353-117">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="60353-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="60353-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="60353-118">See also</span></span>

- [<span data-ttu-id="60353-119">在 Red Hat Enterprise Linux 7 上使用 .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="60353-119">Using .NET Core 3.0 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)
