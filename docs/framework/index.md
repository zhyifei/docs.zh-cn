---
title: .NET Framework 4.7、4.6 和 4.5
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 34402e74bb0cb560d213760c38ce4b936d712eb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="net-framework-guide"></a><span data-ttu-id="76072-102">.NET Framework 指南</span><span class="sxs-lookup"><span data-stu-id="76072-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="76072-103">此 .NET Framework 内容集包含 .NET Framework 4.5、4.5.1、4.5.2、4.6、 4.6.1、 4.6.2、 4.7 和 4.7.1 版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="76072-103">This .NET Framework content set includes information for .NET Framework versions 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, and 4.7.1.</span></span> <span data-ttu-id="76072-104">若要下载 .NET Framework，请参阅[安装 .NET Framework](../../docs/framework/install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="76072-104">To download the .NET Framework, see [Installing the .NET Framework](../../docs/framework/install/guide-for-developers.md).</span></span> <span data-ttu-id="76072-105">有关 NET Framework 4.5、[!INCLUDE[net_v46](../../includes/net-v46-md.md)] 及其次要版本和 .NET Framework 4.7 和 4.7.1 的新增功能和更新列表，请参阅 [.NET Framework 中的新增功能](../../docs/framework/whats-new/index.md)。</span><span class="sxs-lookup"><span data-stu-id="76072-105">For a list of new features and changes in the NET Framework 4.5, the [!INCLUDE[net_v46](../../includes/net-v46-md.md)], their point releases, and the .NET Framework 4.7 and 4.7.1, see [What's New in the .NET Framework](../../docs/framework/whats-new/index.md).</span></span> <span data-ttu-id="76072-106">有关受支持的平台列表，请参阅 [.NET Framework 系统要求](../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76072-106">For a list of supported platforms, see [.NET Framework System Requirements](../../docs/framework/get-started/system-requirements.md).</span></span> 

<span data-ttu-id="76072-107">.NET Framework 是用于为 Web、Windows、Windows Phone、Windows Server 和 Microsoft Azure 构建应用的开发平台。</span><span class="sxs-lookup"><span data-stu-id="76072-107">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="76072-108">它包含公共语言运行时 (CLR) 和 .NET Framework 类库，其中包括各种功能和对许多行业标准的支持。</span><span class="sxs-lookup"><span data-stu-id="76072-108">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="76072-109">.NET Framework 提供许多服务，包括内存管理、类型和内存安全、安全性、网络和应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="76072-109">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="76072-110">它提供易于使用的数据结构和 API，将较低级别的 Windows 操作系统抽象化。</span><span class="sxs-lookup"><span data-stu-id="76072-110">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="76072-111">可在 .NET Framework 中使用各种编程语言，包括 C#、F# 和 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="76072-111">You can use a variety of programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>  

<span data-ttu-id="76072-112">有关适用于用户和开发人员的 .NET Framework 的常规说明，请参阅[入门](../../docs/framework/get-started/index.md)。</span><span class="sxs-lookup"><span data-stu-id="76072-112">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](../../docs/framework/get-started/index.md).</span></span> <span data-ttu-id="76072-113">有关 .NET Framework 的体系结构和主要功能简介，请参阅[概述](../../docs/framework/get-started/overview.md)。</span><span class="sxs-lookup"><span data-stu-id="76072-113">For an introduction to the architecture and key features of the .NET Framework, see the [overview](../../docs/framework/get-started/overview.md).</span></span>  

<span data-ttu-id="76072-114">.NET Framework 可与 [Windows 容器](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)和 Docker 结合使用。</span><span class="sxs-lookup"><span data-stu-id="76072-114">The .NET Framework can be used with Docker and with [Windows Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).</span></span> <span data-ttu-id="76072-115">请参阅[使用 Docker 部署 .NET Framework 应用程序](./docker/index.md)，了解如何在 Docker 容器中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="76072-115">See [Deploying .NET Framework applications with Docker](./docker/index.md) to learn how to run your applications in Docker containers.</span></span>

## <a name="installation"></a><span data-ttu-id="76072-116">安装</span><span class="sxs-lookup"><span data-stu-id="76072-116">Installation</span></span>

<span data-ttu-id="76072-117">.NET Framework 随附于 Windows，使你能够运行 .NET Framework 应用程序。</span><span class="sxs-lookup"><span data-stu-id="76072-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="76072-118">需要的 .NET Framework 版本可能要比 Windows 版本附带的更高。</span><span class="sxs-lookup"><span data-stu-id="76072-118">You may need a later version of the .NET Framework than comes with your Windows version.</span></span> <span data-ttu-id="76072-119">有关详细信息，请参阅[在 Windows 上安装 .NET Framework](./install/index.md)。</span><span class="sxs-lookup"><span data-stu-id="76072-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="76072-120">请参阅[修复 .NET Framework](./install/repair.md)，了解在安装 .NET Framework 时遇到错误时应如何修复 .NET Framework 安装。</span><span class="sxs-lookup"><span data-stu-id="76072-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you are experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="76072-121">若要更详细地了解如何下载 .NET Framework，请参阅[安装面向开发人员的 .NET Framework](../../docs/framework/install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="76072-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76072-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="76072-122">In This Section</span></span>

[<span data-ttu-id="76072-123">新增功能</span><span class="sxs-lookup"><span data-stu-id="76072-123">What's New</span></span>](../../docs/framework/whats-new/index.md)  
<span data-ttu-id="76072-124">描述 .NET Framework 最新版本中的重要新增功能和更改。</span><span class="sxs-lookup"><span data-stu-id="76072-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="76072-125">包含已过时的类型和成员的列表，并提供有关从 .NET Framework 的早期版本中迁移应用程序的指南。</span><span class="sxs-lookup"><span data-stu-id="76072-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="76072-126">入门</span><span class="sxs-lookup"><span data-stu-id="76072-126">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
<span data-ttu-id="76072-127">提供对 .NET Framework 的全面概述和指向其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="76072-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
<span data-ttu-id="76072-128">[迁移指南](../../docs/framework/migration-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="76072-128">[Migration Guide](../../docs/framework/migration-guide/index.md) </span></span>  
<span data-ttu-id="76072-129">如果你正在将应用程序迁移到 .NET Framework 的新版本，请提供资源和所需考虑的更改的列表。</span><span class="sxs-lookup"><span data-stu-id="76072-129">Provides resources and a list of changes you need to consider  if you're migrating your application to a new version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="76072-130">开发指南</span><span class="sxs-lookup"><span data-stu-id="76072-130">Development Guide</span></span>](../../docs/framework/development-guide.md)  
<span data-ttu-id="76072-131">提供了有关应用程序开发的所有关键技术区域和任务（包括创建、配置、调试、保护和部署应用程序）的指南，以及有关动态编程、互操作性、扩展性、内存管理和线程处理的信息。</span><span class="sxs-lookup"><span data-stu-id="76072-131">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
[<span data-ttu-id="76072-132">工具</span><span class="sxs-lookup"><span data-stu-id="76072-132">Tools</span></span>](../../docs/framework/tools/index.md)  
<span data-ttu-id="76072-133">描述有助于使用 .NET Framework 技术开发、配置和部署应用程序的工具。</span><span class="sxs-lookup"><span data-stu-id="76072-133">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>  
  
<span data-ttu-id="76072-134">[.NET Framework 类库](/dotnet/api/?view=netframework-4.7.1) </span><span class="sxs-lookup"><span data-stu-id="76072-134">[.NET Framework Class Library](/dotnet/api/?view=netframework-4.7.1) </span></span>  
<span data-ttu-id="76072-135">提供 .NET Framework 命名空间中包含的每一个类的语法、代码示例和相关信息。</span><span class="sxs-lookup"><span data-stu-id="76072-135">Supplies syntax, code examples, and related information for each class contained in the .NET Framework namespaces.</span></span>  
  
[<span data-ttu-id="76072-136">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="76072-136">Additional Class Libraries and APIs</span></span>](../../docs/framework/additional-apis/index.md)  
<span data-ttu-id="76072-137">收录了非常态 (OOB) 版本中包含的类以及定位特定平台或 .NET Framework 实现代码的类的相关文档。</span><span class="sxs-lookup"><span data-stu-id="76072-137">Provides documentation for classes contained in out-of-band (OOB) releases, as well as for classes that target specific platforms or implementations of the .NET Framework.</span></span>
