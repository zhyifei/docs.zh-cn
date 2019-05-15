---
title: .NET Framework 文档
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d93dea42dbb854d8d52bd5cf3e54d1ce0d892d6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635532"
---
# <a name="net-framework-guide"></a><span data-ttu-id="70538-102">.NET Framework 指南</span><span class="sxs-lookup"><span data-stu-id="70538-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="70538-103">此 .NET Framework 内容集包含 .NET Framework 4.5 到 4.8 版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="70538-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="70538-104">若要下载 .NET Framework，请参阅[安装 .NET Framework](./install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="70538-104">To download the .NET Framework, see [Installing the .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="70538-105">有关 .NET Framework 中的新功能和更改的列表，请参阅 [.NET Framework 中的新增功能](./whats-new/index.md)。</span><span class="sxs-lookup"><span data-stu-id="70538-105">For a list of new features and changes in the NET Framework, see [What's New in the .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="70538-106">有关受支持的平台列表，请参阅 [.NET Framework 系统要求](./get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70538-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="70538-107">有关早期版本的 .NET Framework 的文档，请参阅 [.NET 早期版本文档](https://docs.microsoft.com/previous-versions/dotnet/)。</span><span class="sxs-lookup"><span data-stu-id="70538-107">For documentation about older versions of the .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="70538-108">.NET Framework 是用于为 Web、Windows、Windows Phone、Windows Server 和 Microsoft Azure 构建应用的开发平台。</span><span class="sxs-lookup"><span data-stu-id="70538-108">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="70538-109">它包含公共语言运行时 (CLR) 和 .NET Framework 类库，其中包括各种功能和对许多行业标准的支持。</span><span class="sxs-lookup"><span data-stu-id="70538-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="70538-110">.NET Framework 提供许多服务，包括内存管理、类型和内存安全、安全性、网络和应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="70538-110">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="70538-111">它提供易于使用的数据结构和 API，将较低级别的 Windows 操作系统抽象化。</span><span class="sxs-lookup"><span data-stu-id="70538-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="70538-112">可在 .NET Framework 中使用不同编程语言，包括 C#、F# 和 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="70538-112">You can use different programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="70538-113">有关适用于用户和开发人员的 .NET Framework 的常规说明，请参阅[入门](./get-started/index.md)。</span><span class="sxs-lookup"><span data-stu-id="70538-113">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="70538-114">有关 .NET Framework 的体系结构和主要功能简介，请参阅[概述](./get-started/overview.md)。</span><span class="sxs-lookup"><span data-stu-id="70538-114">For an introduction to the architecture and key features of the .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="70538-115">.NET Framework 可与 [Windows 容器](/virtualization/windowscontainers/about/)和 Docker 结合使用。</span><span class="sxs-lookup"><span data-stu-id="70538-115">The .NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="70538-116">安装</span><span class="sxs-lookup"><span data-stu-id="70538-116">Installation</span></span>

<span data-ttu-id="70538-117">.NET Framework 随附于 Windows，使你能够运行 .NET Framework 应用程序。</span><span class="sxs-lookup"><span data-stu-id="70538-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="70538-118">需要的 .NET Framework 版本可能要比 Windows 版本附带的版本更高。</span><span class="sxs-lookup"><span data-stu-id="70538-118">You may need a later version of the .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="70538-119">有关详细信息，请参阅[在 Windows 上安装 .NET Framework](./install/index.md)。</span><span class="sxs-lookup"><span data-stu-id="70538-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="70538-120">请参阅[修复 .NET Framework](./install/repair.md)，了解在安装 .NET Framework 时遇到错误时应如何修复 .NET Framework 安装。</span><span class="sxs-lookup"><span data-stu-id="70538-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you're experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="70538-121">若要更详细地了解如何下载 .NET Framework，请参阅[安装面向开发人员的 .NET Framework](./install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="70538-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="70538-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="70538-122">In this section</span></span>

* [<span data-ttu-id="70538-123">新增功能</span><span class="sxs-lookup"><span data-stu-id="70538-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="70538-124">描述 .NET Framework 最新版本中的重要新增功能和更改。</span><span class="sxs-lookup"><span data-stu-id="70538-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="70538-125">包含已过时的类型和成员的列表，并提供有关从 .NET Framework 的早期版本中迁移应用程序的指南。</span><span class="sxs-lookup"><span data-stu-id="70538-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="70538-126">入门</span><span class="sxs-lookup"><span data-stu-id="70538-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="70538-127">提供对 .NET Framework 的全面概述和指向其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="70538-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="70538-128">安装指南</span><span class="sxs-lookup"><span data-stu-id="70538-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="70538-129">提供有关 .NET Framework 安装和故障排除的资源和指南。</span><span class="sxs-lookup"><span data-stu-id="70538-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="70538-130">迁移指南</span><span class="sxs-lookup"><span data-stu-id="70538-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="70538-131">如果正在将应用程序迁移到 .NET Framework 的新版本，请提供资源和所需考虑的更改的列表。</span><span class="sxs-lookup"><span data-stu-id="70538-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="70538-132">开发指南</span><span class="sxs-lookup"><span data-stu-id="70538-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="70538-133">提供了有关应用程序开发的所有关键技术区域和任务（包括创建、配置、调试、保护和部署应用程序）的指南，以及有关动态编程、互操作性、扩展性、内存管理和线程处理的信息。</span><span class="sxs-lookup"><span data-stu-id="70538-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="70538-134">工具</span><span class="sxs-lookup"><span data-stu-id="70538-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="70538-135">描述有助于使用 .NET Framework 技术开发、配置和部署应用程序的工具。</span><span class="sxs-lookup"><span data-stu-id="70538-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="70538-136">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="70538-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="70538-137">提供 Microsoft 工具使用的专用 .NET Framework API 的文档。</span><span class="sxs-lookup"><span data-stu-id="70538-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="70538-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="70538-138">See also</span></span>

* [<span data-ttu-id="70538-139">.NET Framework 类库</span><span class="sxs-lookup"><span data-stu-id="70538-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
