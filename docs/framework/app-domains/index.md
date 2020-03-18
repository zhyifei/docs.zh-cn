---
title: 使用应用程序域和程序集编程
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 2c849d27c70971d17bf4359ee7ae1081ee976a5f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73119820"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="5375a-102">使用应用程序域和程序集编程</span><span class="sxs-lookup"><span data-stu-id="5375a-102">Programming with Application Domains and Assemblies</span></span>

<span data-ttu-id="5375a-103">Microsoft Internet Explorer、ASP.NET 和 Windows Shell 等主机将公共语言运行时加载到进程中，在相应进程中创建[应用程序域](application-domains.md)，然后在 .NET Framework 应用程序运行时加载并执行相应应用程序域中的用户代码。</span><span class="sxs-lookup"><span data-stu-id="5375a-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="5375a-104">在大多数情况下，不必担心创建应用程序域和将程序集加载到这些域中，因为运行时主机会执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="5375a-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
<span data-ttu-id="5375a-105">不过，如果要创建将托管公共语言运行时的应用程序、要创建以编程方式卸载的工具/代码或要创建可以动态卸载和重载的可插入组件，需要创建自己的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="5375a-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="5375a-106">即使不要创建运行时主机，也可以参阅本部分，其中介绍了有关如何使用应用程序域和这些应用程序域中加载的程序集的重要信息。</span><span class="sxs-lookup"><span data-stu-id="5375a-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5375a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="5375a-107">In This Section</span></span>  

[<span data-ttu-id="5375a-108">应用程序域和程序集用法主题</span><span class="sxs-lookup"><span data-stu-id="5375a-108">Application Domains and Assemblies How-to Topics</span></span>](application-domains-and-assemblies-how-to-topics.md)  
<span data-ttu-id="5375a-109">收录了使用应用程序域和程序集进行编程的相关概念性文档中的所有用法主题链接。</span><span class="sxs-lookup"><span data-stu-id="5375a-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
[<span data-ttu-id="5375a-110">使用应用程序域</span><span class="sxs-lookup"><span data-stu-id="5375a-110">Using Application Domains</span></span>](use.md)  
<span data-ttu-id="5375a-111">举例说明了如何创建、配置和使用应用程序域。</span><span class="sxs-lookup"><span data-stu-id="5375a-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
[<span data-ttu-id="5375a-112">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="5375a-112">Programming with Assemblies</span></span>](../../standard/assembly/program.md)  
<span data-ttu-id="5375a-113">描述如何在程序集上创建、签署和设置特性。</span><span class="sxs-lookup"><span data-stu-id="5375a-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5375a-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="5375a-114">Related Sections</span></span>  

[<span data-ttu-id="5375a-115">发出动态方法和程序集</span><span class="sxs-lookup"><span data-stu-id="5375a-115">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="5375a-116">描述如何创建动态程序集。</span><span class="sxs-lookup"><span data-stu-id="5375a-116">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="5375a-117">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="5375a-117">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="5375a-118">提供程序集的概念性概述。</span><span class="sxs-lookup"><span data-stu-id="5375a-118">Provides a conceptual overview of assemblies.</span></span>  
  
[<span data-ttu-id="5375a-119">应用程序域</span><span class="sxs-lookup"><span data-stu-id="5375a-119">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="5375a-120">提供应用程序域的概念性概述。</span><span class="sxs-lookup"><span data-stu-id="5375a-120">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="5375a-121">反射概述</span><span class="sxs-lookup"><span data-stu-id="5375a-121">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="5375a-122">介绍了如何使用 **Reflection** 类获取程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="5375a-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
