---
title: "使用应用程序域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eade3728c8a51785214cf3d8de53d8a64a668f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-application-domains"></a><span data-ttu-id="ba66f-102">使用应用程序域</span><span class="sxs-lookup"><span data-stu-id="ba66f-102">Using Application Domains</span></span>
<span data-ttu-id="ba66f-103">应用程序域为公共语言运行时提供隔离单元。</span><span class="sxs-lookup"><span data-stu-id="ba66f-103">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="ba66f-104">它们在进程中创建和运行。</span><span class="sxs-lookup"><span data-stu-id="ba66f-104">They are created and run inside a process.</span></span> <span data-ttu-id="ba66f-105">应用程序域通常由运行时主机创建，运行时主机是一种应用程序，负责向进程加载运行时，并在应用程序域内执行用户代码。</span><span class="sxs-lookup"><span data-stu-id="ba66f-105">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="ba66f-106">运行时主机创建进程和默认应用程序域，并在其中运行托管代码。</span><span class="sxs-lookup"><span data-stu-id="ba66f-106">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="ba66f-107">运行时主机包括 ASP.NET、Microsoft Internet Explorer 和 Windows Shell。</span><span class="sxs-lookup"><span data-stu-id="ba66f-107">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
 <span data-ttu-id="ba66f-108">对大多数应用程序而言，你无需创建自己的应用程序域，运行时主机将为你创建任何所需的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ba66f-108">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="ba66f-109">但是，如果应用程序需要隔离代码或使用和卸载 DLL，则可以创建和配置额外的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ba66f-109">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba66f-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="ba66f-110">In This Section</span></span>  
 [<span data-ttu-id="ba66f-111">如何：创建应用程序域</span><span class="sxs-lookup"><span data-stu-id="ba66f-111">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 <span data-ttu-id="ba66f-112">说明如何以编程方式创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ba66f-112">Describes how to programmatically create an application domain.</span></span>  
  
 [<span data-ttu-id="ba66f-113">如何：卸载应用程序域</span><span class="sxs-lookup"><span data-stu-id="ba66f-113">How to: Unload an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 <span data-ttu-id="ba66f-114">说明如何以编程方式卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ba66f-114">Describes how to programmatically unload an application domain.</span></span>  
  
 [<span data-ttu-id="ba66f-115">如何：配置应用程序域</span><span class="sxs-lookup"><span data-stu-id="ba66f-115">How to: Configure an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 <span data-ttu-id="ba66f-116">提供关于配置应用程序域的简介。</span><span class="sxs-lookup"><span data-stu-id="ba66f-116">Provides an introduction to configuring an application domain.</span></span>  
  
 [<span data-ttu-id="ba66f-117">从应用程序域中检索安装信息</span><span class="sxs-lookup"><span data-stu-id="ba66f-117">Retrieving Setup Information from an Application Domain</span></span>](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 <span data-ttu-id="ba66f-118">说明如何从应用程序域检索安装信息。</span><span class="sxs-lookup"><span data-stu-id="ba66f-118">Describes how to retrieve setup information from an application domain.</span></span>  
  
 [<span data-ttu-id="ba66f-119">如何：将程序集加载到应用程序域中</span><span class="sxs-lookup"><span data-stu-id="ba66f-119">How to: Load Assemblies into an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 <span data-ttu-id="ba66f-120">说明如何将程序集加载到应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="ba66f-120">Describes how to load an assembly into an application domain.</span></span>  
  
 [<span data-ttu-id="ba66f-121">如何：从程序集获取类型和成员信息</span><span class="sxs-lookup"><span data-stu-id="ba66f-121">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="ba66f-122">说明如何检索关于程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="ba66f-122">Describes how to retrieve information about an assembly.</span></span>  
  
 [<span data-ttu-id="ba66f-123">卷影复制程序集</span><span class="sxs-lookup"><span data-stu-id="ba66f-123">Shadow Copying Assemblies</span></span>](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 <span data-ttu-id="ba66f-124">说明卷影复制如何允许对正在使用的程序集进行更新，以及如何配置卷影复制。</span><span class="sxs-lookup"><span data-stu-id="ba66f-124">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
 [<span data-ttu-id="ba66f-125">如何：接收最可能的异常通知</span><span class="sxs-lookup"><span data-stu-id="ba66f-125">How to: Receive First-Chance Exception Notifications</span></span>](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 <span data-ttu-id="ba66f-126">说明在公共语言运行时开始搜索异常处理程序之前，可如何接收已引发异常的通知。</span><span class="sxs-lookup"><span data-stu-id="ba66f-126">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
 [<span data-ttu-id="ba66f-127">解析程序集加载</span><span class="sxs-lookup"><span data-stu-id="ba66f-127">Resolving Assembly Loads</span></span>](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 <span data-ttu-id="ba66f-128">提供有关使用 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 事件处理程序集加载故障的指导。</span><span class="sxs-lookup"><span data-stu-id="ba66f-128">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ba66f-129">参考</span><span class="sxs-lookup"><span data-stu-id="ba66f-129">Reference</span></span>  
 <xref:System.AppDomain>  
 <span data-ttu-id="ba66f-130">表示应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ba66f-130">Represents an application domain.</span></span> <span data-ttu-id="ba66f-131">提供用于创建和控制应用程序域的方法。</span><span class="sxs-lookup"><span data-stu-id="ba66f-131">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ba66f-132">相关章节</span><span class="sxs-lookup"><span data-stu-id="ba66f-132">Related Sections</span></span>  
 <span data-ttu-id="ba66f-133">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="ba66f-133">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>  
 <span data-ttu-id="ba66f-134">概述程序集执行的功能。</span><span class="sxs-lookup"><span data-stu-id="ba66f-134">Provides an overview of the functions performed by assemblies.</span></span>  
  
 [<span data-ttu-id="ba66f-135">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="ba66f-135">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="ba66f-136">描述如何在程序集上创建、签署和设置特性。</span><span class="sxs-lookup"><span data-stu-id="ba66f-136">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
 [<span data-ttu-id="ba66f-137">发出动态方法和程序集</span><span class="sxs-lookup"><span data-stu-id="ba66f-137">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="ba66f-138">描述如何创建动态程序集。</span><span class="sxs-lookup"><span data-stu-id="ba66f-138">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="ba66f-139">应用程序域</span><span class="sxs-lookup"><span data-stu-id="ba66f-139">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="ba66f-140">提供应用程序域的概念性概述。</span><span class="sxs-lookup"><span data-stu-id="ba66f-140">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="ba66f-141">反射概述</span><span class="sxs-lookup"><span data-stu-id="ba66f-141">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="ba66f-142">介绍了如何使用 **Reflection** 类获取程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="ba66f-142">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
