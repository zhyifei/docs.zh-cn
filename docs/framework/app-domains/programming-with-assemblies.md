---
title: "使用程序集编程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 368021062a3ad49d2c63f92797c59b8c0f1cddfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="programming-with-assemblies"></a><span data-ttu-id="2c656-102">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="2c656-102">Programming with Assemblies</span></span>
<span data-ttu-id="2c656-103">程序集是 .NET Framework 的构造块；它们构成了部署、版本控制、重复使用、激活范围和安全权限的基本单元。</span><span class="sxs-lookup"><span data-stu-id="2c656-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="2c656-104">程序集向公共语言运行时提供了解类型实现所需要的信息。</span><span class="sxs-lookup"><span data-stu-id="2c656-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="2c656-105">程序集是为协同工作而生成的类型和资源的集合，这些类型和资源构成了一个逻辑功能单元。</span><span class="sxs-lookup"><span data-stu-id="2c656-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="2c656-106">对于运行时，类型不存在于程序集上下文之外。</span><span class="sxs-lookup"><span data-stu-id="2c656-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="2c656-107">本节说明如何创建模块、根据模块创建程序集、创建密钥对并使用强名称为程序集签名，以及如何将程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="2c656-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="2c656-108">此外，本节还说明如何使用 [MSIL 反汇编程序 (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 查看程序集清单信息。</span><span class="sxs-lookup"><span data-stu-id="2c656-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c656-109">从 .NET Framework 2.0 版开始，对于使用版本号高于当前已加载运行时的 .NET Framework 版本所编译的程序集，运行时将不再加载此类程序集。</span><span class="sxs-lookup"><span data-stu-id="2c656-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="2c656-110">这同样适用于主版本号和次版本号的组合。</span><span class="sxs-lookup"><span data-stu-id="2c656-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c656-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="2c656-111">In This Section</span></span>  
 [<span data-ttu-id="2c656-112">创建程序集</span><span class="sxs-lookup"><span data-stu-id="2c656-112">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="2c656-113">提供单个文件和多文件程序集的概述。</span><span class="sxs-lookup"><span data-stu-id="2c656-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="2c656-114">程序集名称</span><span class="sxs-lookup"><span data-stu-id="2c656-114">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
 <span data-ttu-id="2c656-115">提供程序集命名的概述。</span><span class="sxs-lookup"><span data-stu-id="2c656-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="2c656-116">如何：确定程序集的完全限定的名称</span><span class="sxs-lookup"><span data-stu-id="2c656-116">How to: Determine an Assembly's Fully Qualified Name</span></span>](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 <span data-ttu-id="2c656-117">介绍如何确定程序集的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="2c656-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="2c656-118">以完全信任的形式运行 Intranet 应用程序</span><span class="sxs-lookup"><span data-stu-id="2c656-118">Running Intranet Applications in Full Trust</span></span>](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="2c656-119">介绍如何为 Intranet 共享上的完全信任程序集指定旧安全策略。</span><span class="sxs-lookup"><span data-stu-id="2c656-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="2c656-120">程序集位置</span><span class="sxs-lookup"><span data-stu-id="2c656-120">Assembly Location</span></span>](../../../docs/framework/app-domains/assembly-location.md)  
 <span data-ttu-id="2c656-121">提供查找程序集的概述。</span><span class="sxs-lookup"><span data-stu-id="2c656-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="2c656-122">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="2c656-122">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 <span data-ttu-id="2c656-123">介绍如何创建包含一个文件的程序集。</span><span class="sxs-lookup"><span data-stu-id="2c656-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="2c656-124">多文件程序集</span><span class="sxs-lookup"><span data-stu-id="2c656-124">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="2c656-125">描述创建多文件程序集的原因。</span><span class="sxs-lookup"><span data-stu-id="2c656-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="2c656-126">如何：生成多文件程序集</span><span class="sxs-lookup"><span data-stu-id="2c656-126">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 <span data-ttu-id="2c656-127">介绍如何创建多文件程序集。</span><span class="sxs-lookup"><span data-stu-id="2c656-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="2c656-128">设置程序集特性</span><span class="sxs-lookup"><span data-stu-id="2c656-128">Setting Assembly Attributes</span></span>](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 <span data-ttu-id="2c656-129">介绍程序集属性及其设置方法。</span><span class="sxs-lookup"><span data-stu-id="2c656-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="2c656-130">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="2c656-130">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 <span data-ttu-id="2c656-131">说明使用强名称为程序集进行签名的方法和原因，包括操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="2c656-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="2c656-132">延迟签发程序集</span><span class="sxs-lookup"><span data-stu-id="2c656-132">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 <span data-ttu-id="2c656-133">介绍如何对程序集执行延迟签名。</span><span class="sxs-lookup"><span data-stu-id="2c656-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="2c656-134">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="2c656-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="2c656-135">说明将程序集添加到全局程序集缓存的方法和原因，包括操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="2c656-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="2c656-136">如何：查看程序集内容</span><span class="sxs-lookup"><span data-stu-id="2c656-136">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="2c656-137">介绍如何使用 MSIL 反汇编程序 (Ildasm.exe) 查看程序集内容。</span><span class="sxs-lookup"><span data-stu-id="2c656-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="2c656-138">公共语言运行时中的类型转发</span><span class="sxs-lookup"><span data-stu-id="2c656-138">Type Forwarding in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 <span data-ttu-id="2c656-139">介绍如何在不中断现有应用程序的情况下使用类型转发将类型移动到其他程序集。</span><span class="sxs-lookup"><span data-stu-id="2c656-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2c656-140">参考</span><span class="sxs-lookup"><span data-stu-id="2c656-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="2c656-141">表示程序集的 .NET Framework 类。</span><span class="sxs-lookup"><span data-stu-id="2c656-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2c656-142">相关章节</span><span class="sxs-lookup"><span data-stu-id="2c656-142">Related Sections</span></span>  
 [<span data-ttu-id="2c656-143">如何：从程序集获取类型和成员信息</span><span class="sxs-lookup"><span data-stu-id="2c656-143">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="2c656-144">介绍如何以编程方式从程序集获得类型和其他信息。</span><span class="sxs-lookup"><span data-stu-id="2c656-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 <span data-ttu-id="2c656-145">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="2c656-145">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>  
 <span data-ttu-id="2c656-146">提供公共语言运行时程序集的概念性概述。</span><span class="sxs-lookup"><span data-stu-id="2c656-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="2c656-147">程序集版本控制</span><span class="sxs-lookup"><span data-stu-id="2c656-147">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 <span data-ttu-id="2c656-148">提供程序集绑定以及 <xref:System.Reflection.AssemblyVersionAttribute> 和 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 属性的概述。</span><span class="sxs-lookup"><span data-stu-id="2c656-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="2c656-149">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="2c656-149">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="2c656-150">说明运行时如何确定将用于满足绑定请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="2c656-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 [<span data-ttu-id="2c656-151">反射</span><span class="sxs-lookup"><span data-stu-id="2c656-151">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="2c656-152">介绍了如何使用 **Reflection** 类获取程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="2c656-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
