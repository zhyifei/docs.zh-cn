---
title: .NET Framework 开发指南
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, development guide
ms.assetid: 26e3d285-24c3-435c-a797-9fe5affb8525
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a21f4cd8657a9d2c26ac481e7f2b00e6a2f502c9
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581098"
---
# <a name="net-framework-development-guide"></a><span data-ttu-id="07ab6-102">.NET Framework 开发指南</span><span class="sxs-lookup"><span data-stu-id="07ab6-102">.NET Framework Development Guide</span></span>
<span data-ttu-id="07ab6-103">本节介绍了如何创建、配置、调试、保护和部署 .NET Framework 应用。</span><span class="sxs-lookup"><span data-stu-id="07ab6-103">This section explains how to create, configure, debug, secure, and deploy your .NET Framework apps.</span></span> <span data-ttu-id="07ab6-104">本节还提供有关技术领域的信息，例如，动态编程、互操作性、扩展性、内存管理和线程处理。</span><span class="sxs-lookup"><span data-stu-id="07ab6-104">The section also provides information about technology areas such as dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07ab6-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="07ab6-105">In This Section</span></span>  
 [<span data-ttu-id="07ab6-106">应用程序要点</span><span class="sxs-lookup"><span data-stu-id="07ab6-106">Application Essentials</span></span>](../../docs/standard/application-essentials.md)  
 <span data-ttu-id="07ab6-107">提供有关基本应用开发任务的信息，例如利用应用域和程序集编程、使用特性、格式化和分析基类型、使用集合、处理事件和异常、使用文件和数据流以及使用泛型。</span><span class="sxs-lookup"><span data-stu-id="07ab6-107">Provides information about basic app development tasks, such as programming with app domains and assemblies, using attributes, formatting and parsing base types, using collections, handling events and exceptions, using files and data streams, and using generics.</span></span>  
  
 [<span data-ttu-id="07ab6-108">数据和建模</span><span class="sxs-lookup"><span data-stu-id="07ab6-108">Data and Modeling</span></span>](../../docs/framework/data/index.md)  
 <span data-ttu-id="07ab6-109">提供有关如何使用 ADO.NET、语言集成查询 (LINQ)、WCF 数据服务和 XML 访问数据的信息。</span><span class="sxs-lookup"><span data-stu-id="07ab6-109">Provides information about how to access data using ADO.NET, Language Integrated Query (LINQ), WCF Data Services, and XML.</span></span>  
  
 [<span data-ttu-id="07ab6-110">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="07ab6-110">Client Applications</span></span>](../../docs/framework/develop-client-apps.md)  
 <span data-ttu-id="07ab6-111">介绍如何使用 Windows Presentation Foundation (WPF) 或 Windows 窗体创建基于 Windows 的应用。</span><span class="sxs-lookup"><span data-stu-id="07ab6-111">Explains how to create Windows-based apps by using Windows Presentation Foundation (WPF) or Windows Forms.</span></span>  
  
 [<span data-ttu-id="07ab6-112">使用 ASP.NET 的 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="07ab6-112">Web Applications with ASP.NET</span></span>](../../docs/framework/develop-web-apps-with-aspnet.md)  
 <span data-ttu-id="07ab6-113">提供指向有关使用 ASP.NET 以最少编码生成企业级 Web 应用程序的信息的链接。</span><span class="sxs-lookup"><span data-stu-id="07ab6-113">Provides links to information about using ASP.NET to build enterprise-class web apps with a minimum of coding.</span></span>  
  
 [<span data-ttu-id="07ab6-114">使用 WCF 的面向服务的应用程序</span><span class="sxs-lookup"><span data-stu-id="07ab6-114">Service-Oriented Applications with WCF</span></span>](../../docs/framework/wcf/index.md)  
 <span data-ttu-id="07ab6-115">描述如何使用 Windows Communication Foundation (WCF) 生成安全可靠且面向服务的应用。</span><span class="sxs-lookup"><span data-stu-id="07ab6-115">Describes how to use Windows Communication Foundation (WCF) to build service-oriented apps that are secure and reliable.</span></span>  
  
 <span data-ttu-id="07ab6-116">[使用 Windows Workflow Foundation 生成工作流](windows-workflow-foundation/index.md)   </span><span class="sxs-lookup"><span data-stu-id="07ab6-116">[Building workflows with Windows Workflow Foundation](windows-workflow-foundation/index.md)   </span></span>  
 <span data-ttu-id="07ab6-117">提供有关用于 Windows Workflow Foundation (WF) 的编程模型、示例和工具的信息。</span><span class="sxs-lookup"><span data-stu-id="07ab6-117">Provides information about the programming model, samples, and tools for using Windows Workflow Foundation (WF).</span></span>  

 [<span data-ttu-id="07ab6-118">Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="07ab6-118">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)  
 <span data-ttu-id="07ab6-119">介绍如何使用 Visual Studio 和 .NET Framework 创建作为服务安装的应用，以及如何开始、停止和以其他方式控制其行为。</span><span class="sxs-lookup"><span data-stu-id="07ab6-119">Explains how you can use Visual Studio and the .NET Framework to create an app that is installed as a service, and start, stop, and otherwise control its behavior.</span></span>  
  
 [<span data-ttu-id="07ab6-120">.NET 中的并行处理、并发和异步编程</span><span class="sxs-lookup"><span data-stu-id="07ab6-120">Parallel Processing, Concurrency, and Async Programming in .NET</span></span>](../../docs/standard/parallel-processing-and-concurrency.md)  
 <span data-ttu-id="07ab6-121">提供有关托管线程处理、并行编程和异步编程设计模式的信息。</span><span class="sxs-lookup"><span data-stu-id="07ab6-121">Provides information about managed threading, parallel programming, and asynchronous programming design patterns.</span></span>  
  
 [<span data-ttu-id="07ab6-122">.NET Framework 中的网络编程</span><span class="sxs-lookup"><span data-stu-id="07ab6-122">Network Programming in the .NET Framework</span></span>](../../docs/framework/network-programming/index.md)  
 <span data-ttu-id="07ab6-123">描述 Internet 服务的分层、可扩展和托管实现，你可以将这些服务快速而轻松地集成到你的应用中。</span><span class="sxs-lookup"><span data-stu-id="07ab6-123">Describes the layered, extensible, and managed implementation of Internet services that you can quickly and easily integrate into your apps.</span></span>  
  
 <span data-ttu-id="07ab6-124">[配置 .NET Framework 应用程序](configure-apps/index.md)  </span><span class="sxs-lookup"><span data-stu-id="07ab6-124">[Configuring .NET Framework Apps](configure-apps/index.md)  </span></span>  
 <span data-ttu-id="07ab6-125">介绍如何使用配置文件更改设置，而无需重新编译你的 .NET Framework 应用。</span><span class="sxs-lookup"><span data-stu-id="07ab6-125">Explains how you can use configuration files to change settings without having to recompile your .NET Framework apps.</span></span>  
  
 [<span data-ttu-id="07ab6-126">使用 .NET Native 编译应用程序</span><span class="sxs-lookup"><span data-stu-id="07ab6-126">Compiling Apps with .NET Native</span></span>](../../docs/framework/net-native/index.md)  
 <span data-ttu-id="07ab6-127">介绍如何使用 [!INCLUDE[net_native](../../includes/net-native-md.md)] 预编译技术生成和部署 Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="07ab6-127">Explains how you can use the [!INCLUDE[net_native](../../includes/net-native-md.md)] precompilation technology to build and deploy Windows Store apps.</span></span> [!INCLUDE[net_native](../../includes/net-native-md.md)]<span data-ttu-id="07ab6-128"> 编译在托管代码 (C#) 中编写并使 .NET Framework 面向本机代码的应用。</span><span class="sxs-lookup"><span data-stu-id="07ab6-128"> compiles apps that are written in managed code (C#) and that target the .NET Framework to native code.</span></span>  
  
 [<span data-ttu-id="07ab6-129">安全性</span><span class="sxs-lookup"><span data-stu-id="07ab6-129">Security</span></span>](../../docs/standard/security/index.md)  
 <span data-ttu-id="07ab6-130">提供有关 .NET Framework 中的类和服务的信息，这些类和服务可以帮助确保应用开发的安全。</span><span class="sxs-lookup"><span data-stu-id="07ab6-130">Provides information about the classes and services in the .NET Framework that facilitate secure app development.</span></span>  
  
 [<span data-ttu-id="07ab6-131">调试、跟踪和分析</span><span class="sxs-lookup"><span data-stu-id="07ab6-131">Debugging, Tracing, and Profiling</span></span>](../../docs/framework/debug-trace-profile/index.md)  
 <span data-ttu-id="07ab6-132">介绍如何测试、优化和分析 .NET Framework 应用和应用环境。</span><span class="sxs-lookup"><span data-stu-id="07ab6-132">Explains how to test, optimize, and profile .NET Framework apps and the app environment.</span></span> <span data-ttu-id="07ab6-133">本节包括供管理员和开发人员使用的信息。</span><span class="sxs-lookup"><span data-stu-id="07ab6-133">This section includes information for administrators as well as developers.</span></span>  
  
 [<span data-ttu-id="07ab6-134">开发多平台应用程序</span><span class="sxs-lookup"><span data-stu-id="07ab6-134">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="07ab6-135">介绍有关如何使用 .NET Framework 生成可在手机、桌面和 Web 等多种平台和多种设备之间共享的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="07ab6-135">Provides information about how you can use the .NET Framework to build assemblies that can be shared across multiple platforms and multiple devices such as phones, desktop, and web.</span></span>  
  
 [<span data-ttu-id="07ab6-136">部署</span><span class="sxs-lookup"><span data-stu-id="07ab6-136">Deployment</span></span>](../../docs/framework/deployment/index.md)  
 <span data-ttu-id="07ab6-137">介绍如何打包并分发你的 .NET Framework 应用，包括同时适用于开发人员和管理员的部署指南。</span><span class="sxs-lookup"><span data-stu-id="07ab6-137">Explains how to package and distribute your .NET Framework app, and includes deployment guides for both developers and administrators.</span></span>  
  
 [<span data-ttu-id="07ab6-138">性能</span><span class="sxs-lookup"><span data-stu-id="07ab6-138">Performance</span></span>](../../docs/framework/performance/index.md)  
 <span data-ttu-id="07ab6-139">提供有关缓存、延迟初始化、可靠性和 ETW 事件的信息。</span><span class="sxs-lookup"><span data-stu-id="07ab6-139">Provides information about caching, lazy initialization, reliability, and ETW events.</span></span>  
 
## <a name="reference"></a><span data-ttu-id="07ab6-140">参考</span><span class="sxs-lookup"><span data-stu-id="07ab6-140">Reference</span></span>  
 [<span data-ttu-id="07ab6-141">.NET Framework 类库</span><span class="sxs-lookup"><span data-stu-id="07ab6-141">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.7)  
 <span data-ttu-id="07ab6-142">提供 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 命名空间中包含的每一个类的语法、代码示例和使用信息。</span><span class="sxs-lookup"><span data-stu-id="07ab6-142">Supplies syntax, code examples, and usage information for each class that is contained in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="07ab6-143">相关章节</span><span class="sxs-lookup"><span data-stu-id="07ab6-143">Related Sections</span></span>  
 [<span data-ttu-id="07ab6-144">入门</span><span class="sxs-lookup"><span data-stu-id="07ab6-144">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
 <span data-ttu-id="07ab6-145">提供对 .NET Framework 的全面概述和指向其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="07ab6-145">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
 [<span data-ttu-id="07ab6-146">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ab6-146">What's New</span></span>](../../docs/framework/whats-new/index.md)  
 <span data-ttu-id="07ab6-147">描述最新版本的 .NET Framework 中的重要新增功能和更改。</span><span class="sxs-lookup"><span data-stu-id="07ab6-147">Describes key new features and changes in the latest version of the .NET Framework.</span></span> <span data-ttu-id="07ab6-148">包含新的和已过时的类型和成员的列表，并提供有关从 .NET Framework 的早期版本中迁移应用的指南。</span><span class="sxs-lookup"><span data-stu-id="07ab6-148">Includes lists of new and obsolete types and members, and provides a guide for migrating your apps from the previous version of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="07ab6-149">工具</span><span class="sxs-lookup"><span data-stu-id="07ab6-149">Tools</span></span>](../../docs/framework/tools/index.md)  
 <span data-ttu-id="07ab6-150">描述有助于使用 .NET Framework 技术开发、配置和部署应用的工具。</span><span class="sxs-lookup"><span data-stu-id="07ab6-150">Describes the tools that help you develop, configure, and deploy apps by using .NET Framework technologies.</span></span>  
  
 [<span data-ttu-id="07ab6-151">.NET Framework 示例</span><span class="sxs-lookup"><span data-stu-id="07ab6-151">.NET Framework Samples</span></span>](https://msdn.microsoft.com/library/177055f8-4a1f-43e7-aee6-995c196079b1)  
 <span data-ttu-id="07ab6-152">提供指向演示 .NET Framework 技术的示例应用的 MSDN 代码示例库的链接。</span><span class="sxs-lookup"><span data-stu-id="07ab6-152">Provides links to the MSDN Code Samples Gallery for sample apps that demonstrate .NET Framework technologies.</span></span>
