---
title: 面向 Azure .NET 和 .NET Core 开发人员的工具
description: 获取工具以通过 Windows、Linux 和 Mac 环境开始使用 Azure .NET 库。
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433162"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="5478e-103">面向 .NET 和 .NET Core Azure 开发人员的工具</span><span class="sxs-lookup"><span data-stu-id="5478e-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="5478e-104">SDK 下载</span><span class="sxs-lookup"><span data-stu-id="5478e-104">SDK downloads</span></span>

<span data-ttu-id="5478e-105">用于 .NET 的 Azure 库作为 [NuGet 程序包](https://www.nuget.org/packages?q=windowsazureofficial)实现。</span><span class="sxs-lookup"><span data-stu-id="5478e-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="5478e-106">若要查看 Azure 服务整理的安装说明，请参阅 [API 引用](/dotnet/api/overview/azure/?view=azure-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="5478e-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="5478e-107">开发工具</span><span class="sxs-lookup"><span data-stu-id="5478e-107">Development tools</span></span>

<span data-ttu-id="5478e-108">Visual Studio 内置了用于许多 Azure 服务的工具。</span><span class="sxs-lookup"><span data-stu-id="5478e-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="5478e-109">一些 Azure 服务有其他可用的工具或模拟器，例如 [Azure 存储资源管理器](https://azure.microsoft.com/features/storage-explorer/)。</span><span class="sxs-lookup"><span data-stu-id="5478e-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="5478e-110">如有必要，请参阅适用于你的 Azure 服务的文档，以获取其他工具的信息。</span><span class="sxs-lookup"><span data-stu-id="5478e-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="5478e-111">这些说明会为你的操作系统安装建议的启动开发环境。</span><span class="sxs-lookup"><span data-stu-id="5478e-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="5478e-112">Windows</span><span class="sxs-lookup"><span data-stu-id="5478e-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="5478e-113">Visual Studio 2017 及更高版本针对 Azure 开发提供内置支持。</span><span class="sxs-lookup"><span data-stu-id="5478e-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="5478e-114">下面的步骤介绍了如何在 Visual Studio 中启动 Azure 开发支持。</span><span class="sxs-lookup"><span data-stu-id="5478e-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="5478e-115">对于 Visual Studio 2015 及更早版本，<a href="vs2015-install.md">请按照这些说明操作</a>。</span><span class="sxs-lookup"><span data-stu-id="5478e-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="5478e-116">步骤 1：下载 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5478e-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="5478e-117">如果已安装 Visual Studio 2019，则可跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="5478e-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5478e-118">下载 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5478e-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="5478e-119">步骤 2：安装两个 Azure 工作负荷</span><span class="sxs-lookup"><span data-stu-id="5478e-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="5478e-120">在 Visual Studio 安装程序中，安装 Visual Studio（或修改现有安装）。</span><span class="sxs-lookup"><span data-stu-id="5478e-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="5478e-121">确保已选择“Azure 开发”以及“ASP.NET 和 Web 开发”工作负荷。  </span><span class="sxs-lookup"><span data-stu-id="5478e-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="5478e-122">步骤 3：在 Azure 上使用 .NET 进行开发</span><span class="sxs-lookup"><span data-stu-id="5478e-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="5478e-123">首先，[在 Azure 应用服务中部署第一个 ASP.NET Core Web 应用](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="5478e-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="5478e-124">macOS</span><span class="sxs-lookup"><span data-stu-id="5478e-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="5478e-125">Visual Studio for Mac 提供所需的一切功能用于进行 Azure 开发。</span><span class="sxs-lookup"><span data-stu-id="5478e-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="5478e-126">步骤 1：下载 Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="5478e-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5478e-127">下载 Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="5478e-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="5478e-128">安装时，默认情况下已选择 Azure 工具。</span><span class="sxs-lookup"><span data-stu-id="5478e-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="5478e-129">Linux</span><span class="sxs-lookup"><span data-stu-id="5478e-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="5478e-130">Visual Studio Code 提供所需的一切功能让你在 Linux 上进行 Azure 开发。</span><span class="sxs-lookup"><span data-stu-id="5478e-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="5478e-131">步骤 1：下载 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="5478e-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="5478e-132">用于 .NET Core 应用的 SDK 和命令行工具。</span><span class="sxs-lookup"><span data-stu-id="5478e-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5478e-133">下载 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="5478e-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="5478e-134">步骤 2：Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5478e-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="5478e-135">在任何操作系统上编辑和调试 .NET Core 应用：Windows、Mac 和 Linux。</span><span class="sxs-lookup"><span data-stu-id="5478e-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5478e-136">下载 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5478e-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
