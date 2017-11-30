---
title: "互操作性概述（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: de7ff105de85392fd4b8b342f26e67e89d0d9b96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interoperability-overview-c-programming-guide"></a><span data-ttu-id="c95d0-102">互操作性概述（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c95d0-102">Interoperability Overview (C# Programming Guide)</span></span>
<span data-ttu-id="c95d0-103">本主题描述在 C# 托管代码和非托管代码之间实现互操作性的方法。</span><span class="sxs-lookup"><span data-stu-id="c95d0-103">The topic describes methods to enable interoperability between C# managed code and unmanaged code.</span></span>  
  
## <a name="platform-invoke"></a><span data-ttu-id="c95d0-104">平台调用</span><span class="sxs-lookup"><span data-stu-id="c95d0-104">Platform Invoke</span></span>  
 <span data-ttu-id="c95d0-105">平台调用是一项服务，它使托管代码能够调用动态链接库 (DLL) 中实现的非托管函数，例如 Microsoft Win32 API 中的非托管函数。</span><span class="sxs-lookup"><span data-stu-id="c95d0-105">*Platform invoke* is a service that enables managed code to call unmanaged functions that are implemented in dynamic link libraries (DLLs), such as those in the Microsoft Win32 API.</span></span> <span data-ttu-id="c95d0-106">此服务定位并调用导出的函数，并根据需要跨交互操作边界封送其自变量（整数、字符串、数组、结构等）。</span><span class="sxs-lookup"><span data-stu-id="c95d0-106">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="c95d0-107">有关详细信息，请参阅[使用非托管 DLL 函数](../../../framework/interop/consuming-unmanaged-dll-functions.md)和[如何：使用平台调用播放波形文件](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)。</span><span class="sxs-lookup"><span data-stu-id="c95d0-107">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) and [How to: Use Platform Invoke to Play a Wave File](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c95d0-108">[公共语言运行时](../../../standard/clr.md) (CLR) 管理对系统资源的访问。</span><span class="sxs-lookup"><span data-stu-id="c95d0-108">The [Common Language Runtime](../../../standard/clr.md) (CLR) manages access to system resources.</span></span> <span data-ttu-id="c95d0-109">调用 CLR 外部的非托管代码将避开这种安全机制，因此会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="c95d0-109">Calling unmanaged code that is outside the CLR bypasses this security mechanism, and therefore presents a security risk.</span></span> <span data-ttu-id="c95d0-110">例如，非托管代码可能直接调用非托管代码中的资源，从而避开 CLR 安全机制。</span><span class="sxs-lookup"><span data-stu-id="c95d0-110">For example, unmanaged code might call resources in unmanaged code directly, bypassing CLR security mechanisms.</span></span> <span data-ttu-id="c95d0-111">有关详细信息，请参阅 [.NET Framework 安全性](http://go.microsoft.com/fwlink/?LinkId=37122)。</span><span class="sxs-lookup"><span data-stu-id="c95d0-111">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="c-interop"></a><span data-ttu-id="c95d0-112">C++ 互操作</span><span class="sxs-lookup"><span data-stu-id="c95d0-112">C++ Interop</span></span>  
 <span data-ttu-id="c95d0-113">可使用 C++ interop（又称为 It Just Works (IJW)）包装本机 C++ 类，以便用 C# 或其他 .NET Framework 语言编写的代码可以使用此类。</span><span class="sxs-lookup"><span data-stu-id="c95d0-113">You can use C++ interop, also known as It Just Works (IJW), to wrap a native C++ class so that it can be consumed by code that is authored in C# or another .NET Framework language.</span></span> <span data-ttu-id="c95d0-114">为此，请编写 C++ 代码来包装本机 DLL 或 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="c95d0-114">To do this, you write C++ code to wrap a native DLL or COM component.</span></span> <span data-ttu-id="c95d0-115">与其他 .NET Framework 语言不同，[!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] 具有互操作性支持，可使托管和非托管代码放置在同一个应用程序（甚至同一个文件）中。</span><span class="sxs-lookup"><span data-stu-id="c95d0-115">Unlike other .NET Framework languages, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] has interoperability support that enables managed and unmanaged code to be located in the same application and even in the same file.</span></span> <span data-ttu-id="c95d0-116">然后使用 **/clr** 编译器开关生成托管程序集，以便生成 C++ 代码。</span><span class="sxs-lookup"><span data-stu-id="c95d0-116">You then build the C++ code by using the **/clr** compiler switch to produce a managed assembly.</span></span> <span data-ttu-id="c95d0-117">最后，在 C# 项目中添加一个对该程序集的引用，并像使用其他托管类那样使用被包装对象。</span><span class="sxs-lookup"><span data-stu-id="c95d0-117">Finally, you add a reference to the assembly in your C# project and use the wrapped objects just as you would use other managed classes.</span></span>  
  
## <a name="exposing-com-components-to-c"></a><span data-ttu-id="c95d0-118">向 C# 公开 COM 组件</span><span class="sxs-lookup"><span data-stu-id="c95d0-118">Exposing COM Components to C#</span></span>  
 <span data-ttu-id="c95d0-119">可以使用 C# 项目中的 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="c95d0-119">You can consume a COM component from a C# project.</span></span> <span data-ttu-id="c95d0-120">常规步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="c95d0-120">The general steps are as follows:</span></span>  
  
1.  <span data-ttu-id="c95d0-121">找到要使用的 COM 组件并注册。</span><span class="sxs-lookup"><span data-stu-id="c95d0-121">Locate a COM component to use and register it.</span></span> <span data-ttu-id="c95d0-122">使用 regsvr32.exe 注册或注销 COM DLL。</span><span class="sxs-lookup"><span data-stu-id="c95d0-122">Use regsvr32.exe to register or un–register a COM DLL.</span></span>  
  
2.  <span data-ttu-id="c95d0-123">向项目添加对 COM 组件或类型库的引用。</span><span class="sxs-lookup"><span data-stu-id="c95d0-123">Add to the project a reference to the COM component or type library.</span></span>  
  
     <span data-ttu-id="c95d0-124">添加引用时，[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 使用 [Tlbimp.exe（类型库导入程序）](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)，该导入程序将类型库作为输入，以输出 .NET Framework 互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="c95d0-124">When you add the reference, [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses the [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), which takes a type library as input, to output a .NET Framework interop assembly.</span></span> <span data-ttu-id="c95d0-125">该程序集又称为运行时可调用包装器 (RCW)，其中包含包装类型库中的 COM 类和接口的托管类和接口。</span><span class="sxs-lookup"><span data-stu-id="c95d0-125">The assembly, also named a runtime callable wrapper (RCW), contains managed classes and interfaces that wrap the COM classes and interfaces that are in the type library.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="c95d0-126"> 将对生成程序集的引用添加至项目。</span><span class="sxs-lookup"><span data-stu-id="c95d0-126"> adds to the project a reference to the generated assembly.</span></span>  
  
3.  <span data-ttu-id="c95d0-127">创建在 RCW 中定义的类的实例。</span><span class="sxs-lookup"><span data-stu-id="c95d0-127">Create an instance of a class that is defined in the RCW.</span></span> <span data-ttu-id="c95d0-128">这会创建 COM 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="c95d0-128">This, in turn, creates an instance of the COM object.</span></span>  
  
4.  <span data-ttu-id="c95d0-129">像使用其他托管对象那样使用该对象。</span><span class="sxs-lookup"><span data-stu-id="c95d0-129">Use the object just as you use other managed objects.</span></span> <span data-ttu-id="c95d0-130">当垃圾回收对该对象进行回收后，COM 对象的实例也会从内存中释放出来。</span><span class="sxs-lookup"><span data-stu-id="c95d0-130">When the object is reclaimed by garbage collection, the instance of the COM object is also released from memory.</span></span>  
  
 <span data-ttu-id="c95d0-131">有关详细信息，请参阅[向 .NET Framework 公开 COM 组件](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730)。</span><span class="sxs-lookup"><span data-stu-id="c95d0-131">For more information, see [Exposing COM Components to the .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span></span>  
  
## <a name="exposing-c-to-com"></a><span data-ttu-id="c95d0-132">向 COM 公开 C#</span><span class="sxs-lookup"><span data-stu-id="c95d0-132">Exposing C# to COM</span></span>  
 <span data-ttu-id="c95d0-133">COM 客户端可以使用已经正确公开的 C# 类型。</span><span class="sxs-lookup"><span data-stu-id="c95d0-133">COM clients can consume C# types that have been correctly exposed.</span></span> <span data-ttu-id="c95d0-134">公开 C# 类型的基本步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="c95d0-134">The basic steps to expose C# types are as follows:</span></span>  
  
1.  <span data-ttu-id="c95d0-135">在 C# 项目中添加互操作特性。</span><span class="sxs-lookup"><span data-stu-id="c95d0-135">Add interop attributes in the C# project.</span></span>  
  
     <span data-ttu-id="c95d0-136">可通过修改 [!INCLUDE[csprcs](~/includes/csprcs-md.md)] 项目属性使程序集 COM 可见。</span><span class="sxs-lookup"><span data-stu-id="c95d0-136">You can make an assembly COM visible by modifying [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties.</span></span> <span data-ttu-id="c95d0-137">有关详细信息，请参阅[“程序集信息”对话框](/visualstudio/ide/reference/assembly-information-dialog-box)。</span><span class="sxs-lookup"><span data-stu-id="c95d0-137">For more information, see [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box).</span></span>  
  
2.  <span data-ttu-id="c95d0-138">生成 COM 类型库并对它进行注册以供 COM 使用。</span><span class="sxs-lookup"><span data-stu-id="c95d0-138">Generate a COM type library and register it for COM usage.</span></span>  
  
     <span data-ttu-id="c95d0-139">可修改 [!INCLUDE[csprcs](~/includes/csprcs-md.md)] 项目属性以自动注册 COM 互操作的 C# 程序集。</span><span class="sxs-lookup"><span data-stu-id="c95d0-139">You can modify [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties to automatically register the C# assembly for COM interop.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="c95d0-140"> 使用 [Regasm.exe（程序集注册工具）](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb)方法是使用 `/tlb` 命令行开关，其将托管组件作为输入），以生成类型库。</span><span class="sxs-lookup"><span data-stu-id="c95d0-140"> uses the [Regasm.exe (Assembly Registration Tool)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb), using the `/tlb` command-line switch, which takes a managed assembly as input, to generate a type library.</span></span> <span data-ttu-id="c95d0-141">此类型库描述程序集中的 `public` 类型并添加注册表项，以便 COM 客户端可以创建托管类。</span><span class="sxs-lookup"><span data-stu-id="c95d0-141">This type library describes the `public` types in the assembly and adds registry entries so that COM clients can create managed classes.</span></span>  
  
 <span data-ttu-id="c95d0-142">有关详细信息，请参阅[向 COM 公开 .NET Framework 组件](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6)和 [COM 类示例](../../../csharp/programming-guide/interop/example-com-class.md)。</span><span class="sxs-lookup"><span data-stu-id="c95d0-142">For more information, see [Exposing .NET Framework Components to COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) and [Example COM Class](../../../csharp/programming-guide/interop/example-com-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95d0-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c95d0-143">See Also</span></span>  
 [<span data-ttu-id="c95d0-144">提高互操作的性能</span><span class="sxs-lookup"><span data-stu-id="c95d0-144">Improving Interop Performance</span></span>](http://go.microsoft.com/fwlink/?LinkId=99564)  
 [<span data-ttu-id="c95d0-145">COM 互操作介绍</span><span class="sxs-lookup"><span data-stu-id="c95d0-145">Introduction to COM Interop</span></span>](http://go.microsoft.com/fwlink/?LinkId=112406)  
 [<span data-ttu-id="c95d0-146">托管和非托管代码之间封送处理</span><span class="sxs-lookup"><span data-stu-id="c95d0-146">Marshaling between Managed and Unmanaged Code</span></span>](http://go.microsoft.com/fwlink/?LinkId=112398)  
 [<span data-ttu-id="c95d0-147">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="c95d0-147">Interoperating with Unmanaged Code</span></span>](https://msdn.microsoft.com/library/sd10k43k)  
 [<span data-ttu-id="c95d0-148">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="c95d0-148">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="c95d0-149">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c95d0-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
