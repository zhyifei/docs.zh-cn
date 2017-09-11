---
title: "发出动态方法和程序集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.assetid: 8e8e2631-62fd-40e7-a8ee-0039b06749bc
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c28a5b71a93ea5159adc73316771d490dbe0db87
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="e47c4-102">发出动态方法和程序集</span><span class="sxs-lookup"><span data-stu-id="e47c4-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="e47c4-103">本节介绍 <xref:System.Reflection.Emit> 命名空间中的一组托管类型，它们允许编译器或工具在运行时发出元数据和 Microsoft 中间语言 (MSIL)，并在磁盘上生成可移植可执行 (PE) 文件（可选）。</span><span class="sxs-lookup"><span data-stu-id="e47c4-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="e47c4-104">脚本引擎和编译器是此命名空间的主要使用者。</span><span class="sxs-lookup"><span data-stu-id="e47c4-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="e47c4-105">在本节中，<xref:System.Reflection.Emit> 命名空间提供的功能被称为反射发出。</span><span class="sxs-lookup"><span data-stu-id="e47c4-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="e47c4-106">反射发出具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="e47c4-106">Reflection emit provides the following capabilities:</span></span>  
  
-   <span data-ttu-id="e47c4-107">在运行时定义轻量全局方法（使用 <xref:System.Reflection.Emit.DynamicMethod> 类）并通过委托执行这些方法。</span><span class="sxs-lookup"><span data-stu-id="e47c4-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
-   <span data-ttu-id="e47c4-108">在运行时定义程序集，然后运行程序集以及/或者将程序集保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="e47c4-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="e47c4-109">在运行时定义程序集，运行程序集，然后卸载程序集并允许垃圾回收回收其资源。</span><span class="sxs-lookup"><span data-stu-id="e47c4-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
-   <span data-ttu-id="e47c4-110">在运行时在新的程序集中定义模块，然后运行模块以及/或者将模块保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="e47c4-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="e47c4-111">在运行时在模块中定义类型，创建这些类型的实例并调用其方法。</span><span class="sxs-lookup"><span data-stu-id="e47c4-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
-   <span data-ttu-id="e47c4-112">为已定义模块定义可供工具（如调试器和代码探查器）使用的符号化信息。</span><span class="sxs-lookup"><span data-stu-id="e47c4-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="e47c4-113">除了 <xref:System.Reflection.Emit> 命名空间中的托管类型，还有非托管元数据接口，非托管元数据接口在[元数据接口](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)参考文档中介绍。</span><span class="sxs-lookup"><span data-stu-id="e47c4-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="e47c4-114">托管的反射发出提供比非托管元数据接口更强的语义错误检查和更高级别的元数据抽象。</span><span class="sxs-lookup"><span data-stu-id="e47c4-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="e47c4-115">元数据和 MSIL 的另一个有用资源是《公共语言基础结构 (CLI)》文档，尤其是“第二部分：元数据定义和语义”和“第三部分: CIL 指令集”。</span><span class="sxs-lookup"><span data-stu-id="e47c4-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="e47c4-116">该文档可在 [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) 和 [Ecma 网站](http://go.microsoft.com/fwlink/?LinkId=116487)上联机获取。</span><span class="sxs-lookup"><span data-stu-id="e47c4-116">The documentation is available online on [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](http://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e47c4-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="e47c4-117">In This Section</span></span>  
 [<span data-ttu-id="e47c4-118">反射发出中的安全问题</span><span class="sxs-lookup"><span data-stu-id="e47c4-118">Security Issues in Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
 <span data-ttu-id="e47c4-119">介绍与使用反射发出创建动态程序集相关的安全问题。</span><span class="sxs-lookup"><span data-stu-id="e47c4-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e47c4-120">参考</span><span class="sxs-lookup"><span data-stu-id="e47c4-120">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="e47c4-121">编录可用于生成方法体的 MSIL 指令代码。</span><span class="sxs-lookup"><span data-stu-id="e47c4-121">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="e47c4-122">包含用于发出动态方法、程序集和类型的托管类。</span><span class="sxs-lookup"><span data-stu-id="e47c4-122">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="e47c4-123">介绍 <xref:System.Type> 类，该类代表托管反射和反射发出中的类型，它是使用这些技术的关键。</span><span class="sxs-lookup"><span data-stu-id="e47c4-123">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="e47c4-124">包含用于浏览元数据和托管代码的托管类。</span><span class="sxs-lookup"><span data-stu-id="e47c4-124">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e47c4-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="e47c4-125">Related Sections</span></span>  
 [<span data-ttu-id="e47c4-126">反射</span><span class="sxs-lookup"><span data-stu-id="e47c4-126">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="e47c4-127">说明如何浏览元数据和托管代码。</span><span class="sxs-lookup"><span data-stu-id="e47c4-127">Explains how to explore metadata and managed code.</span></span>  
  
 <span data-ttu-id="e47c4-128">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="e47c4-128">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>  
 <span data-ttu-id="e47c4-129">概述 .NET Framework 中的程序集。</span><span class="sxs-lookup"><span data-stu-id="e47c4-129">Provides an overview of assemblies in the .NET Framework.</span></span>

