---
title: 使用应用程序域和程序集编程
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7124b6b234601e3afc27109ac318f47e3fe40c35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675346"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="811f3-102">使用应用程序域和程序集编程</span><span class="sxs-lookup"><span data-stu-id="811f3-102">Programming with Application Domains and Assemblies</span></span>
<span data-ttu-id="811f3-103">Microsoft Internet Explorer、ASP.NET 和 Windows Shell 等主机将公共语言运行时加载到进程中，在相应进程中创建[应用程序域](../../../docs/framework/app-domains/application-domains.md)，然后在 .NET Framework 应用程序运行时加载并执行相应应用程序域中的用户代码。</span><span class="sxs-lookup"><span data-stu-id="811f3-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](../../../docs/framework/app-domains/application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="811f3-104">在大多数情况下，不必担心创建应用程序域和将程序集加载到这些域中，因为运行时主机会执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="811f3-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
 <span data-ttu-id="811f3-105">不过，如果要创建将托管公共语言运行时的应用程序、要创建以编程方式卸载的工具/代码或要创建可以动态卸载和重载的可插入组件，需要创建自己的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="811f3-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="811f3-106">即使不要创建运行时主机，也可以参阅本部分，其中介绍了有关如何使用应用程序域和这些应用程序域中加载的程序集的重要信息。</span><span class="sxs-lookup"><span data-stu-id="811f3-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="811f3-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="811f3-107">In This Section</span></span>  
 [<span data-ttu-id="811f3-108">应用程序域和程序集用法主题</span><span class="sxs-lookup"><span data-stu-id="811f3-108">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 <span data-ttu-id="811f3-109">收录了使用应用程序域和程序集进行编程的相关概念性文档中的所有用法主题链接。</span><span class="sxs-lookup"><span data-stu-id="811f3-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
 [<span data-ttu-id="811f3-110">使用应用程序域</span><span class="sxs-lookup"><span data-stu-id="811f3-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 <span data-ttu-id="811f3-111">举例说明了如何创建、配置和使用应用程序域。</span><span class="sxs-lookup"><span data-stu-id="811f3-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
 [<span data-ttu-id="811f3-112">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="811f3-112">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="811f3-113">描述如何在程序集上创建、签署和设置特性。</span><span class="sxs-lookup"><span data-stu-id="811f3-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="811f3-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="811f3-114">Related Sections</span></span>  
 [<span data-ttu-id="811f3-115">发出动态方法和程序集</span><span class="sxs-lookup"><span data-stu-id="811f3-115">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="811f3-116">描述如何创建动态程序集。</span><span class="sxs-lookup"><span data-stu-id="811f3-116">Describes how to create dynamic assemblies.</span></span>  
  
 <span data-ttu-id="811f3-117">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="811f3-117">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>  
 <span data-ttu-id="811f3-118">提供程序集的概念性概述。</span><span class="sxs-lookup"><span data-stu-id="811f3-118">Provides a conceptual overview of assemblies.</span></span>  
  
 [<span data-ttu-id="811f3-119">应用程序域</span><span class="sxs-lookup"><span data-stu-id="811f3-119">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="811f3-120">提供应用程序域的概念性概述。</span><span class="sxs-lookup"><span data-stu-id="811f3-120">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="811f3-121">反射概述</span><span class="sxs-lookup"><span data-stu-id="811f3-121">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="811f3-122">介绍了如何使用 **Reflection** 类获取程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="811f3-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
