---
title: .NET 中的安全性
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c3c7eb20bb3368205dab4c7e03b6b80d09a2121
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775278"
---
# <a name="security-in-net"></a><span data-ttu-id="ae1c2-102">.NET 中的安全性</span><span class="sxs-lookup"><span data-stu-id="ae1c2-102">Security in .NET</span></span>

<span data-ttu-id="ae1c2-103">公共语言运行时和 .NET 提供了许多有用的类和服务，使开发人员能够轻松编写安全代码，并让系统管理员能够自定义授予代码的权限，以便它可以访问受保护的资源。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-103">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="ae1c2-104">此外，运行时和 .NET 提供了有用的类和服务，以方便使用加密和基于角色的安全性。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-104">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ae1c2-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="ae1c2-105">In this section</span></span>

- [<span data-ttu-id="ae1c2-106">安全性的基础概念</span><span class="sxs-lookup"><span data-stu-id="ae1c2-106">Key Security Concepts</span></span>](key-security-concepts.md)  
<span data-ttu-id="ae1c2-107">概述公共语言运行时的安全功能。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-107">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="ae1c2-108">本节是开发人员和系统管理员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-108">This section is of interest to developers and system administrators.</span></span>

- [<span data-ttu-id="ae1c2-109">基于角色的安全性</span><span class="sxs-lookup"><span data-stu-id="ae1c2-109">Role-Based Security</span></span>](role-based-security.md)  
<span data-ttu-id="ae1c2-110">描述如何在代码中与基于角色的安全性进行交互。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-110">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="ae1c2-111">本节是开发人员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-111">This section is of interest to developers.</span></span>

- [<span data-ttu-id="ae1c2-112">加密模型</span><span class="sxs-lookup"><span data-stu-id="ae1c2-112">Cryptography Model</span></span>](cryptography-model.md)  
<span data-ttu-id="ae1c2-113">概述 .NET 提供的加密服务。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-113">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="ae1c2-114">本节是开发人员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-114">This section is of interest to developers.</span></span>

- [<span data-ttu-id="ae1c2-115">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="ae1c2-115">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)  
<span data-ttu-id="ae1c2-116">描述创建可靠的 .NET 应用程序的一些最佳实践。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-116">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="ae1c2-117">本节是开发人员感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-117">This section is of interest to developers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="ae1c2-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="ae1c2-118">Related sections</span></span>

[<span data-ttu-id="ae1c2-119">开发指南</span><span class="sxs-lookup"><span data-stu-id="ae1c2-119">Development Guide</span></span>](../../framework/development-guide.md)  
<span data-ttu-id="ae1c2-120">提供了有关应用程序开发的所有关键技术区域和任务（包括创建、配置、调试、保护和部署应用程序）的指南，以及有关动态编程、互操作性、扩展性、内存管理和线程处理的信息。</span><span class="sxs-lookup"><span data-stu-id="ae1c2-120">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
