---
title: "非托管 API 参考"
ms.custom: 
ms.date: 11/06/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- runtime, unmanaged APIs
- common language runtime, unmanaged APIs
- native API reference [.NET Framework]
- unmanaged API reference [.NET Framework]
ms.assetid: 9aa000ee-c04c-492c-ae4f-83ecdf4fdbbe
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a7069762dd95636399c53c98e8bdef6f00be62c1
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="unmanaged-api-reference"></a><span data-ttu-id="1044b-102">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="1044b-102">Unmanaged API Reference</span></span>
<span data-ttu-id="1044b-103">本节包括有关可由与托管代码相关的应用程序（例如运行时主机、编译器、反汇编程序、模糊处理程序、调试器和探查器）使用的非托管 API 的信息。</span><span class="sxs-lookup"><span data-stu-id="1044b-103">This section includes information on unmanaged APIs that can be used by managed-code-related applications, such as runtime hosts, compilers, disassemblers, obfuscators, debuggers, and profilers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1044b-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="1044b-104">In This Section</span></span>  
 [<span data-ttu-id="1044b-105">常见数据类型</span><span class="sxs-lookup"><span data-stu-id="1044b-105">Common Data Types</span></span>](../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)  
 <span data-ttu-id="1044b-106">列出使用的常见数据类型，特别是非托管分析和调试 API 中的常见数据类型。</span><span class="sxs-lookup"><span data-stu-id="1044b-106">Lists the common data types that are used, particularly in the unmanaged profiling and debugging APIs.</span></span>  
  
 [<span data-ttu-id="1044b-107">ALink</span><span class="sxs-lookup"><span data-stu-id="1044b-107">ALink</span></span>](../../../docs/framework/unmanaged-api/alink/index.md)  
 <span data-ttu-id="1044b-108">描述 ALink API，此 API 支持创建 .NET Framework 程序集和未绑定模块。</span><span class="sxs-lookup"><span data-stu-id="1044b-108">Describes the ALink API, which supports the creation of .NET Framework assemblies and unbound modules.</span></span>  
  
 [<span data-ttu-id="1044b-109">验证码</span><span class="sxs-lookup"><span data-stu-id="1044b-109">Authenticode</span></span>](../../../docs/framework/unmanaged-api/authenticode/index.md)  
 <span data-ttu-id="1044b-110">支持验证码 XrML 许可证创建和验证模块。</span><span class="sxs-lookup"><span data-stu-id="1044b-110">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
 [<span data-ttu-id="1044b-111">常量</span><span class="sxs-lookup"><span data-stu-id="1044b-111">Constants</span></span>](../../../docs/framework/unmanaged-api/constants-unmanaged-api-reference.md)  
 <span data-ttu-id="1044b-112">描述在 CorSym.idl 中定义的常量。</span><span class="sxs-lookup"><span data-stu-id="1044b-112">Describes the constants that are defined in CorSym.idl.</span></span>  
  
 [<span data-ttu-id="1044b-113">自定义接口特性</span><span class="sxs-lookup"><span data-stu-id="1044b-113">Custom Interface Attributes</span></span>](http://msdn.microsoft.com/en-us/940952f9-46ad-4a1a-920f-118dc0bdcd9f)  
 <span data-ttu-id="1044b-114">描述组件对象模型 (COM) 的自定义接口特性。</span><span class="sxs-lookup"><span data-stu-id="1044b-114">Describes component object model (COM) custom interface attributes.</span></span>  
  
 [<span data-ttu-id="1044b-115">调试</span><span class="sxs-lookup"><span data-stu-id="1044b-115">Debugging</span></span>](../../../docs/framework/unmanaged-api/debugging/index.md)  
 <span data-ttu-id="1044b-116">描述调试 API，该 API 允许调试器对在公共语言运行时 (CLR) 环境中运行的代码进行调试。</span><span class="sxs-lookup"><span data-stu-id="1044b-116">Describes the debugging API, which enables a debugger to debug code that runs in the common language runtime (CLR) environment.</span></span>  
  
 [<span data-ttu-id="1044b-117">诊断符号存储区</span><span class="sxs-lookup"><span data-stu-id="1044b-117">Diagnostics Symbol Store</span></span>](../../../docs/framework/unmanaged-api/diagnostics/index.md)  
 <span data-ttu-id="1044b-118">描述诊断符号存储区 API，该 API 允许编译器生成符号信息以供调试器使用。</span><span class="sxs-lookup"><span data-stu-id="1044b-118">Describes the diagnostics symbol store API, which enables a compiler to generate symbol information for use by a debugger.</span></span>  
  
 [<span data-ttu-id="1044b-119">合成</span><span class="sxs-lookup"><span data-stu-id="1044b-119">Fusion</span></span>](../../../docs/framework/unmanaged-api/fusion/index.md)  
 <span data-ttu-id="1044b-120">描述合成 API，此 API 允许运行时主机访问应用程序资源的属性，以便为该应用程序查找这些资源的正确版本。</span><span class="sxs-lookup"><span data-stu-id="1044b-120">Describes the fusion API, which enables a runtime host to access the properties of an application's resources in order to locate the correct versions of those resources for the application.</span></span>  
  
 [<span data-ttu-id="1044b-121">承载</span><span class="sxs-lookup"><span data-stu-id="1044b-121">Hosting</span></span>](../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="1044b-122">描述宿主 API，该 API 允许非托管主机将 CLR 集成到其应用程序中。</span><span class="sxs-lookup"><span data-stu-id="1044b-122">Describes the hosting API, which enables unmanaged hosts to integrate the CLR into their applications.</span></span>  
  
 [<span data-ttu-id="1044b-123">元数据</span><span class="sxs-lookup"><span data-stu-id="1044b-123">Metadata</span></span>](../../../docs/framework/unmanaged-api/metadata/index.md)  
 <span data-ttu-id="1044b-124">描述元数据 API，该 API 允许客户端（例如编译器）生成或访问组件的元数据，而无需由 CLR 加载这些类型。</span><span class="sxs-lookup"><span data-stu-id="1044b-124">Describes the metadata API, which enables a client such as a compiler to generate or access a component's metadata without the types being loaded by the CLR.</span></span>  
  
 [<span data-ttu-id="1044b-125">分析</span><span class="sxs-lookup"><span data-stu-id="1044b-125">Profiling</span></span>](../../../docs/framework/unmanaged-api/profiling/index.md)  
 <span data-ttu-id="1044b-126">描述分析 API，该 API 允许探查器监视 CLR 对程序的执行情况。</span><span class="sxs-lookup"><span data-stu-id="1044b-126">Describes the profiling API, which enables a profiler to monitor a program's execution by the CLR.</span></span>  
  
 [<span data-ttu-id="1044b-127">强命名</span><span class="sxs-lookup"><span data-stu-id="1044b-127">Strong Naming</span></span>](../../../docs/framework/unmanaged-api/strong-naming/index.md)  
 <span data-ttu-id="1044b-128">描述强命名 API，该 API 允许客户端管理程序集的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="1044b-128">Describes the strong naming API, which enables a client to administer strong name signing for assemblies.</span></span>  

 [<span data-ttu-id="1044b-129">WMI 和性能计数器</span><span class="sxs-lookup"><span data-stu-id="1044b-129">WMI and Performance Counters</span></span>](wmi/index.md)  
 <span data-ttu-id="1044b-130">描述包装对 Windows Management Instrumentation (WMI) 库的调用的 Api。</span><span class="sxs-lookup"><span data-stu-id="1044b-130">Describes the APIs that wrap calls to Windows Management Instrumentation (WMI) libraries.</span></span>
  
 [<span data-ttu-id="1044b-131">Tlbexp Helper 函数</span><span class="sxs-lookup"><span data-stu-id="1044b-131">Tlbexp Helper Functions</span></span>](../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="1044b-132">描述类型库导出程序 (Tlbexp.exe) 在从程序集到类型库的转换过程中使用的两个 Helper 函数和接口。</span><span class="sxs-lookup"><span data-stu-id="1044b-132">Describes the two helper functions and interface used by the Type Library Exporter (Tlbexp.exe) during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1044b-133">相关章节</span><span class="sxs-lookup"><span data-stu-id="1044b-133">Related Sections</span></span>  
 [<span data-ttu-id="1044b-134">开发指南</span><span class="sxs-lookup"><span data-stu-id="1044b-134">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
  
 [<span data-ttu-id="1044b-135">.NET Framework 高级读物</span><span class="sxs-lookup"><span data-stu-id="1044b-135">Advanced Reading for the .NET Framework</span></span>](http://msdn.microsoft.com/en-us/faae8083-fecb-4514-b133-b0a5a32a7c3c)
