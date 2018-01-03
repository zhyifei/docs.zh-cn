---
title: "调试接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e625818238a1fd18ef3885d2699e0f532efa40e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-interfaces"></a><span data-ttu-id="94211-102">调试接口</span><span class="sxs-lookup"><span data-stu-id="94211-102">Debugging Interfaces</span></span>
<span data-ttu-id="94211-103">本节描述进行程序调试处理的非托管接口，所调试的程序在公共语言运行时 (CLR) 中执行。</span><span class="sxs-lookup"><span data-stu-id="94211-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94211-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="94211-104">In This Section</span></span>  
 [<span data-ttu-id="94211-105">ICLRDataEnumMemoryRegions 接口</span><span class="sxs-lookup"><span data-stu-id="94211-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="94211-106">提供对由调用方指定的内存区域进行枚举的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="94211-107">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="94211-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="94211-108">为 `EnumMemoryRegions` 提供一种回调方法，用于向调试器报告尝试枚举指定内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="94211-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="94211-109">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="94211-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="94211-110">提供与目标 CLR 进程进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="94211-111">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="94211-112">数据访问服务层在目标进程中操作虚拟内存区域时所用的 `ICLRDataTarget` 的子类。</span><span class="sxs-lookup"><span data-stu-id="94211-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="94211-113">ICLRDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="94211-114">一个子类[ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) ，可提供对异常信息的访问。</span><span class="sxs-lookup"><span data-stu-id="94211-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="94211-115">ICLRDebugging 接口</span><span class="sxs-lookup"><span data-stu-id="94211-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="94211-116">提供一些方法，用于处理模块的加载和卸载以进行调试。</span><span class="sxs-lookup"><span data-stu-id="94211-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="94211-117">ICLRDebuggingLibraryProvider 方法</span><span class="sxs-lookup"><span data-stu-id="94211-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="94211-118">包括[ProvideLibrary 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)方法，后者将获取一个库提供程序允许公共语言运行时特定于版本的调试库需要定位和加载上的回调接口。</span><span class="sxs-lookup"><span data-stu-id="94211-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="94211-119">ICLRMetadataLocator 接口</span><span class="sxs-lookup"><span data-stu-id="94211-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="94211-120">数据访问服务层用于在目标进程中定位程序集的元数据的接口。</span><span class="sxs-lookup"><span data-stu-id="94211-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="94211-121">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="94211-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="94211-122">提供允许开发人员在 CLR 环境中调试应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="94211-123">ICorDebugAppDomain Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="94211-124">提供用于调试应用程序域的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="94211-125">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="94211-126">提供处理数组、指针、函数指针和 ByRef 类型的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="94211-127">此接口是 `ICorDebugAppDomain` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="94211-128">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="94211-129">提供用于处理应用程序域中的 [!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="94211-130">此接口是 `ICorDebugAppDomain` 和 `ICorDebugAppDomain2` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="94211-131">ICorDebugAppDomain4 接口</span><span class="sxs-lookup"><span data-stu-id="94211-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="94211-132">合理扩展[ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)接口以从 COM 可调用包装器获取托管的对象。</span><span class="sxs-lookup"><span data-stu-id="94211-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="94211-133">ICorDebugAppDomainEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="94211-134">提供一种方法，此方法从枚举中的下一个位置开始，返回指定数目的 `ICorDebugAppDomain` 值。</span><span class="sxs-lookup"><span data-stu-id="94211-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="94211-135">ICorDebugArrayValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="94211-136">表示一维或多维数组的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="94211-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="94211-137">ICorDebugAssembly Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="94211-138">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="94211-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="94211-139">ICorDebugAssembly2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="94211-140">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="94211-140">Represents an assembly.</span></span> <span data-ttu-id="94211-141">此接口是 `ICorDebugAssembly` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="94211-142">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="94211-143">合理扩展[ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)接口，从而为容器程序集及其包含的程序集提供支持。</span><span class="sxs-lookup"><span data-stu-id="94211-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="94211-144">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-145">ICorDebugAssemblyEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="94211-146">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugAssembly` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="94211-147">ICorDebugBlockingObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="94211-148">有关的列表中提供的枚举器[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="94211-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="94211-149">ICorDebugBoxValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="94211-150">表示装箱的值类对象的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="94211-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="94211-151">ICorDebugBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="94211-152">表示函数中的断点，或值的观察点。</span><span class="sxs-lookup"><span data-stu-id="94211-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="94211-153">ICorDebugBreakpointEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="94211-154">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugBreakpoint` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="94211-155">ICorDebugChain Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="94211-156">表示一个物理或逻辑调用堆栈段。</span><span class="sxs-lookup"><span data-stu-id="94211-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="94211-157">ICorDebugChainEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="94211-158">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugChain` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="94211-159">ICorDebugClass Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="94211-160">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="94211-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="94211-161">如果该类型为泛型类型，则 `ICorDebugClass` 表示实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="94211-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="94211-162">ICorDebugClass2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="94211-163">表示泛型类或具有 <xref:System.Type> 类型的方法参数的类。</span><span class="sxs-lookup"><span data-stu-id="94211-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="94211-164">此接口扩展了 `ICorDebugClass`。</span><span class="sxs-lookup"><span data-stu-id="94211-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="94211-165">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="94211-166">表示 Microsoft 中间语言 (MSIL) 代码段或本机代码段。</span><span class="sxs-lookup"><span data-stu-id="94211-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="94211-167">ICorDebugCode2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="94211-168">提供扩展 `ICorDebugCode` 的功能的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="94211-169">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="94211-170">提供的扩展的方法[ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)和[ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)以提供有关托管返回值的信息。</span><span class="sxs-lookup"><span data-stu-id="94211-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="94211-171">ICorDebugCode4 接口</span><span class="sxs-lookup"><span data-stu-id="94211-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="94211-172">提供使调试器能够枚举的本地变量和函数中的自变量的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="94211-173">ICorDebugCodeEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="94211-174">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugCode` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="94211-175">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="94211-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="94211-176">提供用来检索缓存的接口对象的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="94211-177">ICorDebugContext Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="94211-178">表示一个上下文对象。</span><span class="sxs-lookup"><span data-stu-id="94211-178">Represents a context object.</span></span> <span data-ttu-id="94211-179">此接口尚未实现。</span><span class="sxs-lookup"><span data-stu-id="94211-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="94211-180">ICorDebugController Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="94211-181">表示可以控制代码执行上下文的 <xref:System.Diagnostics.Process> 或 <xref:System.AppDomain> 范围。</span><span class="sxs-lookup"><span data-stu-id="94211-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="94211-182">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="94211-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="94211-183">提供一个回调接口，该接口可提供对特定目标进程的访问。</span><span class="sxs-lookup"><span data-stu-id="94211-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="94211-184">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="94211-185">合理扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="94211-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="94211-186">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-187">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="94211-188">合理扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口以提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="94211-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="94211-189">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-190">ICorDebugDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="94211-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="94211-191">定义所有 `ICorDebug` 调试事件派生的基接口。</span><span class="sxs-lookup"><span data-stu-id="94211-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="94211-192">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-193">ICorDebugEditAndContinueErrorInfo 接口</span><span class="sxs-lookup"><span data-stu-id="94211-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="94211-194">已过时。</span><span class="sxs-lookup"><span data-stu-id="94211-194">Obsolete.</span></span> <span data-ttu-id="94211-195">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="94211-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="94211-196">ICorDebugEditAndContinueSnapshot Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="94211-197">已过时。</span><span class="sxs-lookup"><span data-stu-id="94211-197">Obsolete.</span></span> <span data-ttu-id="94211-198">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="94211-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="94211-199">ICorDebugEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="94211-200">作为调试枚举器的抽象基接口。</span><span class="sxs-lookup"><span data-stu-id="94211-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="94211-201">ICorDebugErrorInfoEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="94211-202">已过时。</span><span class="sxs-lookup"><span data-stu-id="94211-202">Obsolete.</span></span> <span data-ttu-id="94211-203">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="94211-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="94211-204">ICorDebugEval Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="94211-205">提供使调试器能够在正在调试的代码的上下文中执行代码的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="94211-206">ICorDebugEval2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="94211-207">扩展 `ICorDebugEval` 以对泛型类型提供支持。</span><span class="sxs-lookup"><span data-stu-id="94211-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="94211-208">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="94211-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="94211-209">扩展[icor 调试调试事件](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)接口以支持异常事件。</span><span class="sxs-lookup"><span data-stu-id="94211-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="94211-210">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-211">ICorDebugExceptionObjectCallStackEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="94211-212">为嵌入在异常对象中的调用堆栈信息提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="94211-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="94211-213">ICorDebugExceptionObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="94211-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="94211-214">扩展[ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)接口以提供来自托管的异常对象的堆栈跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="94211-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="94211-215">ICorDebugFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="94211-216">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="94211-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="94211-217">ICorDebugFrameEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="94211-218">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugFrame` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="94211-219">ICorDebugFunction Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="94211-220">表示一个托管函数或方法。</span><span class="sxs-lookup"><span data-stu-id="94211-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="94211-221">ICorDebugFunction2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="94211-222">对 `ICorDebugFunction` 进行逻辑扩展，以支持“仅我的代码”的单步执行调试。</span><span class="sxs-lookup"><span data-stu-id="94211-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="94211-223">ICorDebugFunction3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="94211-224">合理扩展[ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)接口以提供对代码的访问，ReJIT 请求中。</span><span class="sxs-lookup"><span data-stu-id="94211-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="94211-225">ICorDebugFunctionBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="94211-226">扩展 `ICorDebugBreakpoint` 以支持函数中的断点。</span><span class="sxs-lookup"><span data-stu-id="94211-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="94211-227">ICorDebugGCReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="94211-228">提供针对将进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="94211-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="94211-229">ICorDebugGenericValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="94211-230">应用于所有值的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="94211-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="94211-231">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="94211-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="94211-232">ICorDebugGuidToTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="94211-233">提供针对映射 GUID 的对象及其相应的 `ICorDebugType` 对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="94211-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="94211-234">ICorDebugHandleValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="94211-235">`ICorDebugReferenceValue` 的一个子类，前者表示调试器已为其创建了垃圾回收句柄的引用值。</span><span class="sxs-lookup"><span data-stu-id="94211-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="94211-236">ICorDebugHeapEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="94211-237">提供针对托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="94211-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="94211-238">ICorDebugHeapSegmentEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="94211-239">提供针对托管堆的内存区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="94211-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="94211-240">ICorDebugHeapValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="94211-241">表示 CLR 垃圾回收器已收集的对象的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="94211-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="94211-242">ICorDebugHeapValue2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="94211-243">对运行时句柄提供支持的 `ICorDebugHeapValue` 的扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="94211-244">ICorDebugHeapValue3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="94211-245">公开对象的监视器锁属性。</span><span class="sxs-lookup"><span data-stu-id="94211-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="94211-246">ICorDebugILCode 接口</span><span class="sxs-lookup"><span data-stu-id="94211-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="94211-247">表示中间语言 (IL) 代码段。</span><span class="sxs-lookup"><span data-stu-id="94211-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="94211-248">ICorDebugILCode2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="94211-249">合理扩展[ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)接口，以提供的方法，返回的标记的函数的局部变量签名，并将探查器检测到的中间语言 (IL) 偏移量到原始方法的 IL偏移量。</span><span class="sxs-lookup"><span data-stu-id="94211-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="94211-250">ICorDebugILFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="94211-251">表示 MSIL 代码的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="94211-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="94211-252">ICorDebugILFrame2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="94211-253">`ICorDebugILFrame` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="94211-254">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="94211-255">提供用于封装函数的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="94211-256">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="94211-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="94211-257">提供使你能够访问中间语言 (IL) 代码的堆栈帧中的局部变量和代码的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="94211-258">一个用于指定调试器是否可以访问在探查器 ReJIT 检测中添加的变量和代码的参数。</span><span class="sxs-lookup"><span data-stu-id="94211-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="94211-259">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="94211-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="94211-260">表示某一实例字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="94211-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="94211-261">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-262">ICorDebugInternalFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="94211-263">标识调试器的帧类型。</span><span class="sxs-lookup"><span data-stu-id="94211-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="94211-264">ICorDebugInternalFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="94211-265">提供有关内部帧，包括堆栈地址和相对于位置的信息[ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="94211-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="94211-266">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="94211-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="94211-267">提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="94211-267">Provides information about a loaded module.</span></span> <span data-ttu-id="94211-268">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-269">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="94211-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="94211-270">提供用于处理调试器回调的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="94211-271">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="94211-272">提供支持调试器异常处理和托管调试助手 (MDA) 的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="94211-273">`ICorDebugManagedCallback2` 是 `ICorDebugManagedCallback` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="94211-274">ICorDebugManagedCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="94211-275">提供一个回调方法，该方法指示已发出启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="94211-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="94211-276">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="94211-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="94211-277">表示托管调试助手 (MDA) 消息。</span><span class="sxs-lookup"><span data-stu-id="94211-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="94211-278">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="94211-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="94211-279">表示内存中缓冲区。</span><span class="sxs-lookup"><span data-stu-id="94211-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="94211-280">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-281">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="94211-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="94211-282">提供有关合并的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="94211-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="94211-283">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-284">ICorDebugMetaDataLocator 接口</span><span class="sxs-lookup"><span data-stu-id="94211-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="94211-285">向调试器提供元数据信息。</span><span class="sxs-lookup"><span data-stu-id="94211-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="94211-286">ICorDebugModule Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="94211-287">表示 CLR 模块，它是可执行文件或动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="94211-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="94211-288">ICorDebugModule2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="94211-289">用作 `ICorDebugModule` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="94211-290">ICorDebugModule3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="94211-291">为动态模块创建符号读取器。</span><span class="sxs-lookup"><span data-stu-id="94211-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="94211-292">ICorDebugModuleBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="94211-293">扩展 `ICorDebugBreakpoint` 以提供对特定模块的访问。</span><span class="sxs-lookup"><span data-stu-id="94211-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="94211-294">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="94211-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="94211-295">扩展[icor 调试调试事件](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="94211-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="94211-296">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-297">ICorDebugModuleEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="94211-298">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugModule` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="94211-299">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="94211-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="94211-300">扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口以支持可变数据目标。</span><span class="sxs-lookup"><span data-stu-id="94211-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="94211-301">ICorDebugNativeFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="94211-302">用于本机帧的 `ICorDebugFrame` 的专用实现。</span><span class="sxs-lookup"><span data-stu-id="94211-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="94211-303">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="94211-304">提供用于测试子帧与父帧关系的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="94211-305">ICorDebugObjectEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="94211-306">实现 `ICorDebugEnum` 方法，并通过对象数组的相对虚拟地址 (RVA) 对其进行枚举。</span><span class="sxs-lookup"><span data-stu-id="94211-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="94211-307">ICorDebugObjectValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="94211-308">表示包含对象的值的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="94211-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="94211-309">ICorDebugObjectValue2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="94211-310">扩展 `ICorDebugObjectValue` 以支持继承和重写。</span><span class="sxs-lookup"><span data-stu-id="94211-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="94211-311">ICorDebugProcess Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="94211-312">表示正在执行托管代码的进程。</span><span class="sxs-lookup"><span data-stu-id="94211-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="94211-313">ICorDebugProcess2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="94211-314">`ICorDebugProcess` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="94211-315">ICorDebugProcess3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="94211-316">控制自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="94211-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="94211-317">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="94211-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="94211-318">扩展[ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)接口以支持对托管堆，提供有关垃圾回收的托管对象的信息并确定调试器是否从应用程序加载映像的访问的本地本机映像缓存中。</span><span class="sxs-lookup"><span data-stu-id="94211-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="94211-319">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="94211-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="94211-320">合理扩展[ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)接口以启用解码托管的调试事件的编码在本机异常调试事件和虚拟模块拆分等功能。</span><span class="sxs-lookup"><span data-stu-id="94211-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="94211-321">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-322">ICorDebugProcess7 接口</span><span class="sxs-lookup"><span data-stu-id="94211-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="94211-323">提供了一种方法，用于配置调试器以处理目标进程中的内存中元数据更新。</span><span class="sxs-lookup"><span data-stu-id="94211-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="94211-324">ICorDebugProcess8 接口</span><span class="sxs-lookup"><span data-stu-id="94211-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="94211-325">合理扩展[ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)接口以启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="94211-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="94211-326">ICorDebugProcessEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="94211-327">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugProcess` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="94211-328">ICorDebugReferenceValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="94211-329">`ICorDebugValue` 的子类，它支持引用类型。</span><span class="sxs-lookup"><span data-stu-id="94211-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="94211-330">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="94211-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="94211-331">表示在当前正在执行代码的计算机上可用的寄存器组。</span><span class="sxs-lookup"><span data-stu-id="94211-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="94211-332">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="94211-333">为具有 64 个以上寄存器的硬件平台扩展 `ICorDebugRegisterSet` 的功能。</span><span class="sxs-lookup"><span data-stu-id="94211-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="94211-334">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="94211-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="94211-335">提供启动托管调试器或将其附加到远程目标进程的能力。</span><span class="sxs-lookup"><span data-stu-id="94211-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="94211-336">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="94211-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="94211-337">提供使你能够在 CLR 环境中调试基于 Silverlight 的应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="94211-338">ICorDebugRuntimeUnwindableFrame 接口</span><span class="sxs-lookup"><span data-stu-id="94211-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="94211-339">提供对非托管方法的支持，这些方法需要公共语言运行时 (CLR) 来展开帧。</span><span class="sxs-lookup"><span data-stu-id="94211-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="94211-340">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="94211-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="94211-341">提供用于获取线程堆栈上的托管方法或帧的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="94211-342">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="94211-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="94211-343">表示某个静态字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="94211-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="94211-344">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-345">ICorDebugStepper Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="94211-346">表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。</span><span class="sxs-lookup"><span data-stu-id="94211-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="94211-347">ICorDebugStepper2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="94211-348">提供对“仅我的代码”(JMC) 调试的支持。</span><span class="sxs-lookup"><span data-stu-id="94211-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="94211-349">ICorDebugStepperEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="94211-350">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugStepper` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="94211-351">ICorDebugStringValue Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="94211-352">应用于字符串值的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="94211-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="94211-353">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="94211-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="94211-354">提供可用于检索调试符号信息的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="94211-355">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-356">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="94211-357">合理扩展[ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)接口以检索其他调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="94211-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="94211-358">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-359">ICorDebugThread Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="94211-360">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="94211-360">Represents a thread in a process.</span></span> <span data-ttu-id="94211-361">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="94211-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="94211-362">ICorDebugThread2 Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="94211-363">用作 `ICorDebugThread` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="94211-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="94211-364">ICorDebugThread3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="94211-365">提供的入口点[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)和相应接口。</span><span class="sxs-lookup"><span data-stu-id="94211-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="94211-366">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="94211-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="94211-367">提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="94211-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="94211-368">ICorDebugThreadEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="94211-369">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugThread` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="94211-370">ICorDebugType Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="94211-371">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="94211-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="94211-372">如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="94211-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="94211-373">ICorDebugType2 接口</span><span class="sxs-lookup"><span data-stu-id="94211-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="94211-374">扩展[ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)接口以检索的基类型或复杂 （用户定义的） 类型的类型标识符。</span><span class="sxs-lookup"><span data-stu-id="94211-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="94211-375">ICorDebugTypeEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="94211-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="94211-376">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugType` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="94211-377">ICorDebugUnmanagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="94211-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="94211-378">提供与 CLR 没有直接关系的本机事件的通知。</span><span class="sxs-lookup"><span data-stu-id="94211-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="94211-379">"ICorDebugValue"</span><span class="sxs-lookup"><span data-stu-id="94211-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="94211-380">表示正在调试的进程中的读取或写入值。</span><span class="sxs-lookup"><span data-stu-id="94211-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="94211-381">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="94211-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="94211-382">扩展 `ICorDebugValue` 以提供对 `ICorDebugType` 的支持。</span><span class="sxs-lookup"><span data-stu-id="94211-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="94211-383">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="94211-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="94211-384">扩展"ICorDebugValue"和"ICorDebugValue2"接口，以支持大于 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="94211-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="94211-385">"ICorDebugValueBreakpoint"</span><span class="sxs-lookup"><span data-stu-id="94211-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="94211-386">扩展 `ICorDebugBreakpoint` 以提供对特定值的访问。</span><span class="sxs-lookup"><span data-stu-id="94211-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="94211-387">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="94211-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="94211-388">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugValue` 数组。</span><span class="sxs-lookup"><span data-stu-id="94211-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="94211-389">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="94211-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="94211-390">表示本地变量或函数参数。</span><span class="sxs-lookup"><span data-stu-id="94211-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="94211-391">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="94211-392">提供对本地变量和函数中的参数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="94211-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="94211-393">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="94211-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="94211-394">检索变量的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="94211-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="94211-395">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-396">ICorDebugVirtualUnwinder 接口</span><span class="sxs-lookup"><span data-stu-id="94211-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="94211-397">提供帮助堆栈展开的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="94211-398">**在仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="94211-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="94211-399">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="94211-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="94211-400">用作发布进程的常规接口。</span><span class="sxs-lookup"><span data-stu-id="94211-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="94211-401">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="94211-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="94211-402">表示并提供关于应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="94211-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="94211-403">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="94211-404">提供遍历进程中当前存在的 `ICorPublishAppDomain` 对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="94211-405">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="94211-406">用作发布枚举器的抽象基。</span><span class="sxs-lookup"><span data-stu-id="94211-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="94211-407">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="94211-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="94211-408">提供用于访问有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="94211-409">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="94211-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="94211-410">提供遍历 `ICorPublishProcess` 对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="94211-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="94211-411">相关章节</span><span class="sxs-lookup"><span data-stu-id="94211-411">Related Sections</span></span>  
 [<span data-ttu-id="94211-412">调试组件类</span><span class="sxs-lookup"><span data-stu-id="94211-412">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="94211-413">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="94211-413">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="94211-414">调试枚举</span><span class="sxs-lookup"><span data-stu-id="94211-414">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="94211-415">调试结构</span><span class="sxs-lookup"><span data-stu-id="94211-415">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
