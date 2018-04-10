---
title: .NET Framework 中的安全性
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- .NET Framework, security
- security [.NET Framework], about security
- application development [.NET Framework], security
- security [.NET Framework]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
caps.latest.revision: 37
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7f8600da624ff75ce2dbd5c417f886d6b3b1ac37
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="security-in-the-net-framework"></a><span data-ttu-id="f5488-102">.NET Framework 中的安全性</span><span class="sxs-lookup"><span data-stu-id="f5488-102">Security in the .NET Framework</span></span>
<span data-ttu-id="f5488-103">公共语言运行时和 .NET Framework 提供许多有用的类和服务，让开发人员能够轻松编写安全代码，并让系统管理员能够自定义对代码授予的权限，使代码可以访问受保护的资源。</span><span class="sxs-lookup"><span data-stu-id="f5488-103">The common language runtime and the .NET Framework provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="f5488-104">此外，运行时和 .NET Framework 提供了有用的类和服务，以方便使用加密和基于角色的安全性。</span><span class="sxs-lookup"><span data-stu-id="f5488-104">In addition, the runtime and the .NET Framework provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5488-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="f5488-105">In This Section</span></span>  
 [<span data-ttu-id="f5488-106">安全更改</span><span class="sxs-lookup"><span data-stu-id="f5488-106">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)  
 <span data-ttu-id="f5488-107">描述对 .NET Framework 安全系统进行的重要更改。</span><span class="sxs-lookup"><span data-stu-id="f5488-107">Describes important changes to the .NET Framework security system.</span></span>  
  
 [<span data-ttu-id="f5488-108">安全性的基础概念</span><span class="sxs-lookup"><span data-stu-id="f5488-108">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="f5488-109">概述公共语言运行时的安全功能。</span><span class="sxs-lookup"><span data-stu-id="f5488-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="f5488-110">本节是开发人员和系统管理员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="f5488-110">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="f5488-111">基于角色的安全性</span><span class="sxs-lookup"><span data-stu-id="f5488-111">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="f5488-112">描述如何在代码中与基于角色的安全性进行交互。</span><span class="sxs-lookup"><span data-stu-id="f5488-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="f5488-113">本节是开发人员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="f5488-113">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="f5488-114">加密模型</span><span class="sxs-lookup"><span data-stu-id="f5488-114">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="f5488-115">概述 .NET Framework 提供的加密服务。</span><span class="sxs-lookup"><span data-stu-id="f5488-115">Provides an overview of cryptographic services provided by the .NET Framework.</span></span> <span data-ttu-id="f5488-116">本节是开发人员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="f5488-116">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="f5488-117">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="f5488-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="f5488-118">描述创建可靠的.NET Framework 应用程序的一些最佳做法。</span><span class="sxs-lookup"><span data-stu-id="f5488-118">Describes some of the best practices for creating reliable .NET Framework applications.</span></span> <span data-ttu-id="f5488-119">本节是开发人员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="f5488-119">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="f5488-120">非托管代码的安全编码指南</span><span class="sxs-lookup"><span data-stu-id="f5488-120">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="f5488-121">描述在调用非托管代码时的一些最佳做法和安全问题。</span><span class="sxs-lookup"><span data-stu-id="f5488-121">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="f5488-122">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="f5488-122">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="f5488-123">描述如何在应用程序中实现基于声明的标识。</span><span class="sxs-lookup"><span data-stu-id="f5488-123">Describes how you can implement claims-based identity in your applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f5488-124">相关章节</span><span class="sxs-lookup"><span data-stu-id="f5488-124">Related Sections</span></span>  
 [<span data-ttu-id="f5488-125">开发指南</span><span class="sxs-lookup"><span data-stu-id="f5488-125">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="f5488-126">提供了有关应用程序开发的所有关键技术区域和任务（包括创建、配置、调试、保护和部署应用程序）的指南，以及有关动态编程、互操作性、扩展性、内存管理和线程处理的信息。</span><span class="sxs-lookup"><span data-stu-id="f5488-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
