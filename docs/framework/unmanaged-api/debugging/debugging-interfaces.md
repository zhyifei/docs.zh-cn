---
title: 调试接口
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d939063aaefb00d4db3de604df0dbd1b2175bf95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698416"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="d8917-102">调试接口</span><span class="sxs-lookup"><span data-stu-id="d8917-102">Debugging Interfaces</span></span>
<span data-ttu-id="d8917-103">本节描述进行程序调试处理的非托管接口，所调试的程序在公共语言运行时 (CLR) 中执行。</span><span class="sxs-lookup"><span data-stu-id="d8917-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8917-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="d8917-104">In This Section</span></span>  
 <span data-ttu-id="d8917-105">[ICLRDataEnumMemoryRegions 接口](iclrdataenummemoryregions-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)\\</span></span>
 <span data-ttu-id="d8917-106">提供对由调用方指定的内存区域进行枚举的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="d8917-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\\</span></span>
 <span data-ttu-id="d8917-108">为 `EnumMemoryRegions` 提供一种回调方法，用于向调试器报告尝试枚举指定内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="d8917-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="d8917-109">[ICLRDataTarget 接口](iclrdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="d8917-110">提供与目标 CLR 进程进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="d8917-111">[ICLRDataTarget2 接口](iclrdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-112">数据访问服务层在目标进程中操作虚拟内存区域时所用的 `ICLRDataTarget` 的子类。</span><span class="sxs-lookup"><span data-stu-id="d8917-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="d8917-113">[ICLRDataTarget3 接口](iclrdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-114">子类[ICLRDataTarget2](iclrdatatarget2-interface.md)提供对异常信息的访问。</span><span class="sxs-lookup"><span data-stu-id="d8917-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="d8917-115">[ICLRDebugging 接口](iclrdebugging-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-115">[ICLRDebugging Interface](iclrdebugging-interface.md)\\</span></span>
 <span data-ttu-id="d8917-116">提供一些方法，用于处理模块的加载和卸载以进行调试。</span><span class="sxs-lookup"><span data-stu-id="d8917-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="d8917-117">[ICLRDebuggingLibraryProvider 接口](iclrdebugginglibraryprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)\\</span></span>
 <span data-ttu-id="d8917-118">包括[ProvideLibrary 方法](iclrdebugginglibraryprovider-providelibrary-method.md)方法，获取一个库提供程序允许公共语言运行时特定于版本的调试库定位和加载根据需要的回调接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="d8917-119">[ICLRMetadataLocator 接口](iclrmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="d8917-120">数据访问服务层用于在目标进程中定位程序集的元数据的接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="d8917-121">[ICorDebug 接口](icordebug-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-121">[ICorDebug Interface](icordebug-interface.md)\\</span></span>
 <span data-ttu-id="d8917-122">提供允许开发人员在 CLR 环境中调试应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="d8917-123">[ICorDebugAppDomain 接口](icordebugappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)\\</span></span>
 <span data-ttu-id="d8917-124">提供用于调试应用程序域的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="d8917-125">[ICorDebugAppDomain2 接口](icordebugappdomain2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-126">提供处理数组、指针、函数指针和 ByRef 类型的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="d8917-127">此接口是 `ICorDebugAppDomain` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="d8917-128">[ICorDebugAppDomain3 接口](icordebugappdomain3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-129">提供用于处理应用程序域中的 [!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="d8917-130">此接口是 `ICorDebugAppDomain` 和 `ICorDebugAppDomain2` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="d8917-131">[ICorDebugAppDomain4 接口](icordebugappdomain4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\\</span></span>
 <span data-ttu-id="d8917-132">进行逻辑扩展[ICorDebugAppDomain](icordebugappdomain-interface.md)接口，用于从 COM 可调用包装器获取托管的对象。</span><span class="sxs-lookup"><span data-stu-id="d8917-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="d8917-133">[ICorDebugAppDomainEnum 接口](icordebugappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-134">提供一种方法，此方法从枚举中的下一个位置开始，返回指定数目的 `ICorDebugAppDomain` 值。</span><span class="sxs-lookup"><span data-stu-id="d8917-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="d8917-135">[ICorDebugArrayValue 接口](icordebugarrayvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-136">表示一维或多维数组的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="d8917-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="d8917-137">[ICorDebugAssembly 接口](icordebugassembly-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)\\</span></span>
 <span data-ttu-id="d8917-138">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="d8917-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="d8917-139">[ICorDebugAssembly2 接口](icordebugassembly2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-140">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="d8917-140">Represents an assembly.</span></span> <span data-ttu-id="d8917-141">此接口是 `ICorDebugAssembly` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="d8917-142">[ICorDebugAssembly3 接口](icordebugassembly3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-143">进行逻辑扩展[icor 调试程序集](icordebugassembly-interface.md)接口以便为容器程序集和其包含的程序集提供支持。</span><span class="sxs-lookup"><span data-stu-id="d8917-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="d8917-144">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-145">[ICorDebugAssemblyEnum 接口](icordebugassemblyenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-146">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugAssembly` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="d8917-147">[ICorDebugBlockingObjectEnum 接口](icordebugblockingobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-148">提供的枚举器的列表[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="d8917-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="d8917-149">[ICorDebugBoxValue 接口](icordebugboxvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-150">表示装箱的值类对象的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="d8917-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="d8917-151">[ICorDebugBreakpoint 接口](icordebugbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="d8917-152">表示函数中的断点，或值的观察点。</span><span class="sxs-lookup"><span data-stu-id="d8917-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="d8917-153">[ICorDebugBreakpointEnum 接口](icordebugbreakpointenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-154">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugBreakpoint` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="d8917-155">[ICorDebugChain 接口](icordebugchain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-155">[ICorDebugChain Interface](icordebugchain-interface.md)\\</span></span>
 <span data-ttu-id="d8917-156">表示一个物理或逻辑调用堆栈段。</span><span class="sxs-lookup"><span data-stu-id="d8917-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="d8917-157">[ICorDebugChainEnum 接口](icordebugchainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-158">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugChain` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="d8917-159">[ICorDebugClass 接口](icordebugclass-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-159">[ICorDebugClass Interface](icordebugclass-interface.md)\\</span></span>
 <span data-ttu-id="d8917-160">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="d8917-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="d8917-161">如果该类型为泛型类型，则 `ICorDebugClass` 表示实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="d8917-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="d8917-162">[ICorDebugClass2 接口](icordebugclass2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-163">表示泛型类或具有 <xref:System.Type> 类型的方法参数的类。</span><span class="sxs-lookup"><span data-stu-id="d8917-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="d8917-164">此接口扩展了 `ICorDebugClass`。</span><span class="sxs-lookup"><span data-stu-id="d8917-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="d8917-165">[ICorDebugCode 接口](icordebugcode-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-165">[ICorDebugCode Interface](icordebugcode-interface1.md)\\</span></span>
 <span data-ttu-id="d8917-166">表示 Microsoft 中间语言 (MSIL) 代码段或本机代码段。</span><span class="sxs-lookup"><span data-stu-id="d8917-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="d8917-167">[ICorDebugCode2 接口](icordebugcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-168">提供扩展 `ICorDebugCode` 的功能的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="d8917-169">[ICorDebugCode3 接口](icordebugcode3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-170">提供扩展方法[ICorDebugCode](icordebugcode-interface1.md)并[ICorDebugCode2](icordebugcode2-interface.md)以提供有关托管返回值信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="d8917-171">[ICorDebugCode4 接口](icordebugcode4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)\\</span></span>
 <span data-ttu-id="d8917-172">提供使调试器能够枚举本地变量和函数中的参数的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="d8917-173">[ICorDebugCodeEnum 接口](icordebugcodeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-174">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugCode` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="d8917-175">[ICorDebugComObjectValue 接口](icordebugcomobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-176">提供用来检索缓存的接口对象的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="d8917-177">[ICorDebugContext 接口](icordebugcontext-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-177">[ICorDebugContext Interface](icordebugcontext-interface.md)\\</span></span>
 <span data-ttu-id="d8917-178">表示一个上下文对象。</span><span class="sxs-lookup"><span data-stu-id="d8917-178">Represents a context object.</span></span> <span data-ttu-id="d8917-179">此接口尚未实现。</span><span class="sxs-lookup"><span data-stu-id="d8917-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="d8917-180">[ICorDebugController 接口](icordebugcontroller-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-180">[ICorDebugController Interface](icordebugcontroller-interface.md)\\</span></span>
 <span data-ttu-id="d8917-181">表示可以控制代码执行上下文的 <xref:System.Diagnostics.Process> 或 <xref:System.AppDomain> 范围。</span><span class="sxs-lookup"><span data-stu-id="d8917-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="d8917-182">[ICorDebugDataTarget 接口](icordebugdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="d8917-183">提供一个回调接口，该接口可提供对特定目标进程的访问。</span><span class="sxs-lookup"><span data-stu-id="d8917-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="d8917-184">[ICorDebugDataTarget2 接口](icordebugdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-185">进行逻辑扩展[ICorDebugDataTarget](icordebugdatatarget-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="d8917-186">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-187">[ICorDebugDataTarget3 接口](icordebugdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-188">进行逻辑扩展[ICorDebugDataTarget](icordebugdatatarget-interface.md)接口以提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="d8917-189">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-190">[ICorDebugDebugEvent 接口](icordebugdebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)\\</span></span>
 <span data-ttu-id="d8917-191">定义所有 `ICorDebug` 调试事件派生的基接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="d8917-192">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-193">[ICorDebugEditAndContinueErrorInfo 接口](icordebugeditandcontinueerrorinfo-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\\</span></span>
 <span data-ttu-id="d8917-194">已过时。</span><span class="sxs-lookup"><span data-stu-id="d8917-194">Obsolete.</span></span> <span data-ttu-id="d8917-195">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="d8917-196">[ICorDebugEditAndContinueSnapshot 接口](icordebugeditandcontinuesnapshot-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)\\</span></span>
 <span data-ttu-id="d8917-197">已过时。</span><span class="sxs-lookup"><span data-stu-id="d8917-197">Obsolete.</span></span> <span data-ttu-id="d8917-198">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="d8917-199">[ICorDebugEnum 接口](icordebugenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)\\</span></span>
 <span data-ttu-id="d8917-200">作为调试枚举器的抽象基接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="d8917-201">[ICorDebugErrorInfoEnum 接口](icordebugerrorinfoenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-202">已过时。</span><span class="sxs-lookup"><span data-stu-id="d8917-202">Obsolete.</span></span> <span data-ttu-id="d8917-203">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="d8917-204">[ICorDebugEval 接口](icordebugeval-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-204">[ICorDebugEval Interface](icordebugeval-interface.md)\\</span></span>
 <span data-ttu-id="d8917-205">提供使调试器能够在正在调试的代码的上下文中执行代码的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="d8917-206">[ICorDebugEval2 接口](icordebugeval2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-207">扩展 `ICorDebugEval` 以对泛型类型提供支持。</span><span class="sxs-lookup"><span data-stu-id="d8917-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="d8917-208">[ICorDebugExceptionDebugEvent 接口](icordebugexceptiondebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)\\</span></span>
 <span data-ttu-id="d8917-209">扩展了[icor 调试调试事件](icordebugdebugevent-interface.md)接口以支持异常事件。</span><span class="sxs-lookup"><span data-stu-id="d8917-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="d8917-210">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-211">[ICorDebugExceptionObjectCallStackEnum 接口](icordebugexceptionobjectcallstackenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-212">为嵌入在异常对象中的调用堆栈信息提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="d8917-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="d8917-213">[ICorDebugExceptionObjectValue 接口](icordebugexceptionobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-214">扩展了[ICorDebugObjectValue](icordebugobjectvalue-interface.md)接口，以提供从托管的异常对象的堆栈跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="d8917-215">[ICorDebugFrame 接口](icordebugframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-215">[ICorDebugFrame Interface](icordebugframe-interface.md)\\</span></span>
 <span data-ttu-id="d8917-216">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="d8917-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="d8917-217">[ICorDebugFrameEnum 接口](icordebugframeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-218">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugFrame` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="d8917-219">[ICorDebugFunction 接口](icordebugfunction-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)\\</span></span>
 <span data-ttu-id="d8917-220">表示一个托管函数或方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="d8917-221">[ICorDebugFunction2 接口](icordebugfunction2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-222">对 `ICorDebugFunction` 进行逻辑扩展，以支持“仅我的代码”的单步执行调试。</span><span class="sxs-lookup"><span data-stu-id="d8917-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="d8917-223">[ICorDebugFunction3 接口](icordebugfunction3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-224">进行逻辑扩展[ICorDebugFunction](icordebugfunction-interface1.md)接口以提供对代码访问权限，ReJIT 请求中。</span><span class="sxs-lookup"><span data-stu-id="d8917-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="d8917-225">[ICorDebugFunctionBreakpoint 接口](icordebugfunctionbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="d8917-226">扩展 `ICorDebugBreakpoint` 以支持函数中的断点。</span><span class="sxs-lookup"><span data-stu-id="d8917-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="d8917-227">[ICorDebugGCReferenceEnum 接口](icordebuggcreferenceenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-228">提供针对将进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d8917-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="d8917-229">[ICorDebugGenericValue 接口](icordebuggenericvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-230">应用于所有值的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="d8917-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="d8917-231">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="d8917-232">[ICorDebugGuidToTypeEnum 接口](icordebugguidtotypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-233">提供针对映射 GUID 的对象及其相应的 `ICorDebugType` 对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d8917-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="d8917-234">[ICorDebugHandleValue 接口](icordebughandlevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-235">`ICorDebugReferenceValue` 的一个子类，前者表示调试器已为其创建了垃圾回收句柄的引用值。</span><span class="sxs-lookup"><span data-stu-id="d8917-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="d8917-236">[ICorDebugHeapEnum 接口](icordebugheapenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-237">提供针对托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d8917-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="d8917-238">[ICorDebugHeapSegmentEnum 接口](icordebugheapsegmentenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-239">提供针对托管堆的内存区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d8917-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="d8917-240">[ICorDebugHeapValue 接口](icordebugheapvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-241">表示 CLR 垃圾回收器已收集的对象的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="d8917-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="d8917-242">[ICorDebugHeapValue2 接口](icordebugheapvalue2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)\\</span></span>
 <span data-ttu-id="d8917-243">对运行时句柄提供支持的 `ICorDebugHeapValue` 的扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="d8917-244">[ICorDebugHeapValue3 接口](icordebugheapvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-245">公开对象的监视器锁属性。</span><span class="sxs-lookup"><span data-stu-id="d8917-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="d8917-246">[ICorDebugILCode 接口](icordebugilcode-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)\\</span></span>
 <span data-ttu-id="d8917-247">表示中间语言 (IL) 代码段。</span><span class="sxs-lookup"><span data-stu-id="d8917-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="d8917-248">[ICorDebugILCode2 接口](icordebugilcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-249">进行逻辑扩展[ICorDebugILCode](icordebugilcode-interface.md)接口，以提供的方法的返回函数的局部变量签名，该标记和映射将探查器检测中间语言 (IL) 偏移量到原始方法的 IL偏移量。</span><span class="sxs-lookup"><span data-stu-id="d8917-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="d8917-250">[ICorDebugILFrame 接口](icordebugilframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)\\</span></span>
 <span data-ttu-id="d8917-251">表示 MSIL 代码的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="d8917-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="d8917-252">[ICorDebugILFrame2 接口](icordebugilframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-253">`ICorDebugILFrame` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="d8917-254">[ICorDebugILFrame3 接口](icordebugilframe3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-255">提供用于封装函数的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="d8917-256">[ICorDebugILFrame4 接口](icordebugilframe4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)\\</span></span>
 <span data-ttu-id="d8917-257">提供使你能够访问中间语言 (IL) 代码的堆栈帧中的局部变量和代码的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="d8917-258">一个用于指定调试器是否可以访问在探查器 ReJIT 检测中添加的变量和代码的参数。</span><span class="sxs-lookup"><span data-stu-id="d8917-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="d8917-259">[ICorDebugInstanceFieldSymbol 接口](icordebuginstancefieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="d8917-260">表示某一实例字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="d8917-261">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-262">[ICorDebugInternalFrame 接口](icordebuginternalframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)\\</span></span>
 <span data-ttu-id="d8917-263">标识调试器的帧类型。</span><span class="sxs-lookup"><span data-stu-id="d8917-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="d8917-264">[ICorDebugInternalFrame2 接口](icordebuginternalframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-265">提供有关内部帧，包括堆栈地址和相对于位置的信息[ICorDebugFrame](icordebugframe-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="d8917-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="d8917-266">[ICorDebugLoadedModule 接口](icordebugloadedmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)\\</span></span>
 <span data-ttu-id="d8917-267">提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-267">Provides information about a loaded module.</span></span> <span data-ttu-id="d8917-268">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="d8917-270">提供用于处理调试器回调的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="d8917-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-272">提供支持调试器异常处理和托管调试助手 (MDA) 的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="d8917-273">`ICorDebugManagedCallback2` 是 `ICorDebugManagedCallback` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="d8917-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-275">提供一个回调方法，该方法指示已发出启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="d8917-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="d8917-276">[ICorDebugMDA 接口](icordebugmda-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-276">[ICorDebugMDA Interface](icordebugmda-interface.md)\\</span></span>
 <span data-ttu-id="d8917-277">表示托管调试助手 (MDA) 消息。</span><span class="sxs-lookup"><span data-stu-id="d8917-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="d8917-278">[ICorDebugMemoryBuffer 接口](icordebugmemorybuffer-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)\\</span></span>
 <span data-ttu-id="d8917-279">表示内存中缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d8917-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="d8917-280">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-281">[ICorDebugMergedAssemblyRecord 接口](icordebugmergedassemblyrecord-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)\\</span></span>
 <span data-ttu-id="d8917-282">提供有关合并的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="d8917-283">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-284">[ICorDebugMetaDataLocator 接口](icordebugmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="d8917-285">向调试器提供元数据信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="d8917-286">[ICorDebugModule 接口](icordebugmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-286">[ICorDebugModule Interface](icordebugmodule-interface.md)\\</span></span>
 <span data-ttu-id="d8917-287">表示 CLR 模块，它是可执行文件或动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="d8917-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="d8917-288">[ICorDebugModule2 接口](icordebugmodule2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-289">用作 `ICorDebugModule` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="d8917-290">[ICorDebugModule3 接口](icordebugmodule3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-291">为动态模块创建符号读取器。</span><span class="sxs-lookup"><span data-stu-id="d8917-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="d8917-292">[ICorDebugModuleBreakpoint 接口](icordebugmodulebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="d8917-293">扩展 `ICorDebugBreakpoint` 以提供对特定模块的访问。</span><span class="sxs-lookup"><span data-stu-id="d8917-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="d8917-294">[ICorDebugModuleDebugEvent 接口](icordebugmoduledebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)\\</span></span>
 <span data-ttu-id="d8917-295">扩展了[icor 调试调试事件](icordebugdebugevent-interface.md)接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="d8917-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="d8917-296">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-298">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugModule` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="d8917-299">[ICorDebugMutableDataTarget 接口](icordebugmutabledatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)\\</span></span>
 <span data-ttu-id="d8917-300">扩展了[ICorDebugDataTarget](icordebugdatatarget-interface.md)接口以支持可变数据目标。</span><span class="sxs-lookup"><span data-stu-id="d8917-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="d8917-301">[ICorDebugNativeFrame 接口](icordebugnativeframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)\\</span></span>
 <span data-ttu-id="d8917-302">用于本机帧的 `ICorDebugFrame` 的专用实现。</span><span class="sxs-lookup"><span data-stu-id="d8917-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="d8917-303">[ICorDebugNativeFrame2 接口](icordebugnativeframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-304">提供用于测试子帧与父帧关系的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="d8917-305">[ICorDebugObjectEnum 接口](icordebugobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-306">实现 `ICorDebugEnum` 方法，并通过对象数组的相对虚拟地址 (RVA) 对其进行枚举。</span><span class="sxs-lookup"><span data-stu-id="d8917-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="d8917-307">[ICorDebugObjectValue 接口](icordebugobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-308">表示包含对象的值的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="d8917-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="d8917-309">[ICorDebugObjectValue2 接口](icordebugobjectvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-310">扩展 `ICorDebugObjectValue` 以支持继承和重写。</span><span class="sxs-lookup"><span data-stu-id="d8917-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="d8917-311">[ICorDebugProcess 接口](icordebugprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)\\</span></span>
 <span data-ttu-id="d8917-312">表示正在执行托管代码的进程。</span><span class="sxs-lookup"><span data-stu-id="d8917-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="d8917-313">[ICorDebugProcess2 接口](icordebugprocess2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)\\</span></span>
 <span data-ttu-id="d8917-314">`ICorDebugProcess` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="d8917-315">[ICorDebugProcess3 接口](icordebugprocess3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-316">控制自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="d8917-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="d8917-317">[ICorDebugProcess4 接口](icordebugprocess4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)\\</span></span>
 <span data-ttu-id="d8917-318">提供对进程执行失控的支持。</span><span class="sxs-lookup"><span data-stu-id="d8917-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="d8917-319">[ICorDebugProcess5 接口](icordebugprocess5-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)\\</span></span>
 <span data-ttu-id="d8917-320">扩展了[ICorDebugProcess](icordebugprocess-interface.md)接口以支持对托管堆，以提供有关垃圾回收的托管对象的信息并确定调试器是否加载图像从应用程序访问的本地本机映像缓存。</span><span class="sxs-lookup"><span data-stu-id="d8917-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="d8917-321">[ICorDebugProcess6 接口](icordebugprocess6-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)\\</span></span>
 <span data-ttu-id="d8917-322">进行逻辑扩展[ICorDebugProcess](icordebugprocess-interface.md)接口以启用解码托管的调试事件的本机异常调试事件和虚拟模块拆分中编码等功能。</span><span class="sxs-lookup"><span data-stu-id="d8917-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="d8917-323">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-324">[ICorDebugProcess7 接口](icordebugprocess7-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)\\</span></span>
 <span data-ttu-id="d8917-325">提供了一种方法，用于配置调试器以处理目标进程中的内存中元数据更新。</span><span class="sxs-lookup"><span data-stu-id="d8917-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="d8917-326">[ICorDebugProcess8 接口](icordebugprocess8-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)\\</span></span>
 <span data-ttu-id="d8917-327">进行逻辑扩展[ICorDebugProcess](icordebugprocess-interface.md)接口以启用或禁用某些类型的[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="d8917-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="d8917-328">[ICorDebugProcessEnum 接口](icordebugprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-329">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugProcess` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="d8917-330">[ICorDebugReferenceValue 接口](icordebugreferencevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-331">`ICorDebugValue` 的子类，它支持引用类型。</span><span class="sxs-lookup"><span data-stu-id="d8917-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="d8917-332">[ICorDebugRegisterSet 接口](icordebugregisterset-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)\\</span></span>
 <span data-ttu-id="d8917-333">表示在当前正在执行代码的计算机上可用的寄存器组。</span><span class="sxs-lookup"><span data-stu-id="d8917-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="d8917-334">[ICorDebugRegisterSet2 接口](icordebugregisterset2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-335">为具有 64 个以上寄存器的硬件平台扩展 `ICorDebugRegisterSet` 的功能。</span><span class="sxs-lookup"><span data-stu-id="d8917-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="d8917-336">[ICorDebugRemote 接口](icordebugremote-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-336">[ICorDebugRemote Interface](icordebugremote-interface.md)\\</span></span>
 <span data-ttu-id="d8917-337">提供启动托管调试器或将其附加到远程目标进程的能力。</span><span class="sxs-lookup"><span data-stu-id="d8917-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="d8917-338">[ICorDebugRemoteTarget 接口](icordebugremotetarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)\\</span></span>
 <span data-ttu-id="d8917-339">提供使你能够在 CLR 环境中调试基于 Silverlight 的应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="d8917-340">[ICorDebugRuntimeUnwindableFrame 接口](icordebugruntimeunwindableframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)\\</span></span>
 <span data-ttu-id="d8917-341">提供对非托管方法的支持，这些方法需要公共语言运行时 (CLR) 来展开帧。</span><span class="sxs-lookup"><span data-stu-id="d8917-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="d8917-342">[ICorDebugStackWalk 接口](icordebugstackwalk-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)\\</span></span>
 <span data-ttu-id="d8917-343">提供用于获取线程堆栈上的托管方法或帧的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="d8917-344">[ICorDebugStaticFieldSymbol 接口](icordebugstaticfieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="d8917-345">表示某个静态字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="d8917-346">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-347">[ICorDebugStepper 接口](icordebugstepper-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)\\</span></span>
 <span data-ttu-id="d8917-348">表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。</span><span class="sxs-lookup"><span data-stu-id="d8917-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="d8917-349">[ICorDebugStepper2 接口](icordebugstepper2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)\\</span></span>
 <span data-ttu-id="d8917-350">提供对“仅我的代码”(JMC) 调试的支持。</span><span class="sxs-lookup"><span data-stu-id="d8917-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="d8917-351">[ICorDebugStepperEnum 接口](icordebugstepperenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-352">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugStepper` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="d8917-353">[ICorDebugStringValue 接口](icordebugstringvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-354">应用于字符串值的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="d8917-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="d8917-355">[ICorDebugSymbolProvider 接口](icordebugsymbolprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)\\</span></span>
 <span data-ttu-id="d8917-356">提供可用于检索调试符号信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="d8917-357">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-358">[ICorDebugSymbolProvider2 接口](icordebugsymbolprovider2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-359">进行逻辑扩展[ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)接口来检索其他调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="d8917-360">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-361">[ICorDebugThread 接口](icordebugthread-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-361">[ICorDebugThread Interface](icordebugthread-interface.md)\\</span></span>
 <span data-ttu-id="d8917-362">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="d8917-362">Represents a thread in a process.</span></span> <span data-ttu-id="d8917-363">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="d8917-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="d8917-364">[ICorDebugThread2 接口](icordebugthread2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-365">用作 `ICorDebugThread` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="d8917-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="d8917-366">[ICorDebugThread3 接口](icordebugthread3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-367">提供的入口点[ICorDebugStackWalk](icordebugstackwalk-interface.md)和相应的接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="d8917-368">[ICorDebugThread4 接口](icordebugthread4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)\\</span></span>
 <span data-ttu-id="d8917-369">提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="d8917-370">[ICorDebugThreadEnum 接口](icordebugthreadenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)\\</span></span>
 <span data-ttu-id="d8917-371">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugThread` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="d8917-372">[ICorDebugType 接口](icordebugtype-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-372">[ICorDebugType Interface](icordebugtype-interface.md)\\</span></span>
 <span data-ttu-id="d8917-373">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="d8917-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="d8917-374">如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="d8917-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="d8917-375">[ICorDebugType2 接口](icordebugtype2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-376">扩展了[ICorDebugType](icordebugtype-interface.md)接口来检索的基类型或复杂 （用户定义的） 类型的类型标识符。</span><span class="sxs-lookup"><span data-stu-id="d8917-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="d8917-377">[ICorDebugTypeEnum 接口](icordebugtypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-378">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugType` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="d8917-379">[ICorDebugUnmanagedCallback 接口](icordebugunmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="d8917-380">提供与 CLR 没有直接关系的本机事件的通知。</span><span class="sxs-lookup"><span data-stu-id="d8917-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="d8917-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span></span>
 <span data-ttu-id="d8917-382">表示正在调试的进程中的读取或写入值。</span><span class="sxs-lookup"><span data-stu-id="d8917-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="d8917-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span></span>
 <span data-ttu-id="d8917-384">扩展 `ICorDebugValue` 以提供对 `ICorDebugType` 的支持。</span><span class="sxs-lookup"><span data-stu-id="d8917-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="d8917-385">[ICorDebugValue3 接口](icordebugvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)\\</span></span>
 <span data-ttu-id="d8917-386">扩展了"ICorDebugValue"和"ICorDebugValue2"的接口以支持大于 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="d8917-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="d8917-388">扩展 `ICorDebugBreakpoint` 以提供对特定值的访问。</span><span class="sxs-lookup"><span data-stu-id="d8917-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="d8917-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-390">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugValue` 数组。</span><span class="sxs-lookup"><span data-stu-id="d8917-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="d8917-391">[ICorDebugVariableHome 接口](icordebugvariablehome-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)\\</span></span>
 <span data-ttu-id="d8917-392">表示本地变量或函数的参数。</span><span class="sxs-lookup"><span data-stu-id="d8917-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="d8917-393">[ICorDebugVariableHomeEnum 接口](icordebugvariablehomeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-394">提供对本地变量和函数的参数个数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d8917-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="d8917-395">[ICorDebugVariableSymbol 接口](icordebugvariablesymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)\\</span></span>
 <span data-ttu-id="d8917-396">检索变量的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="d8917-397">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-398">[ICorDebugVirtualUnwinder 接口](icordebugvirtualunwinder-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)\\</span></span>
 <span data-ttu-id="d8917-399">提供帮助堆栈展开的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="d8917-400">**仅.NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="d8917-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="d8917-401">[ICorPublish 接口](icorpublish-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-401">[ICorPublish Interface](icorpublish-interface.md)\\</span></span>
 <span data-ttu-id="d8917-402">用作发布进程的常规接口。</span><span class="sxs-lookup"><span data-stu-id="d8917-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="d8917-403">[ICorPublishAppDomain 接口](icorpublishappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)\\</span></span>
 <span data-ttu-id="d8917-404">表示并提供关于应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="d8917-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="d8917-405">[ICorPublishAppDomainEnum 接口](icorpublishappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-406">提供遍历进程中当前存在的 `ICorPublishAppDomain` 对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="d8917-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-408">用作发布枚举器的抽象基。</span><span class="sxs-lookup"><span data-stu-id="d8917-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="d8917-409">[ICorPublishProcess 接口](icorpublishprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)\\</span></span>
 <span data-ttu-id="d8917-410">提供用于访问有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="d8917-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="d8917-412">提供遍历 `ICorPublishProcess` 对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="d8917-413">[ISOSDacInterface 接口](isosdacinterface-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)\\</span></span>
 <span data-ttu-id="d8917-414">访问的数据提供帮助器方法`SOS`。</span><span class="sxs-lookup"><span data-stu-id="d8917-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="d8917-415">[IXCLRDataMethodDefinition 接口](ixclrdatamethoddefinition-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)\\</span></span>
 <span data-ttu-id="d8917-416">提供用于查询方法定义的有关信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="d8917-417">[IXCLRDataMethodInstance 接口](ixclrdatamethodinstance-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)\\</span></span>
 <span data-ttu-id="d8917-418">提供用于查询方法实例的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="d8917-419">[IXCLRDataModule 接口](ixclrdatamodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)\\</span></span>
 <span data-ttu-id="d8917-420">提供用于查询有关加载的模块的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="d8917-421">[IXCLRDataProcess 接口](ixclrdataprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\\</span></span>
 <span data-ttu-id="d8917-422">提供用于查询有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d8917-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="d8917-423">相关章节</span><span class="sxs-lookup"><span data-stu-id="d8917-423">Related Sections</span></span>  
 <span data-ttu-id="d8917-424">[调试组件类](debugging-coclasses.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-424">[Debugging Coclasses](debugging-coclasses.md)\\</span></span>
 <span data-ttu-id="d8917-425">[调试全局静态函数](debugging-global-static-functions.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-425">[Debugging Global Static Functions](debugging-global-static-functions.md)\\</span></span>
 <span data-ttu-id="d8917-426">[调试枚举](debugging-enumerations.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-426">[Debugging Enumerations](debugging-enumerations.md)\\</span></span>
 <span data-ttu-id="d8917-427">[调试结构](debugging-structures.md)\\</span><span class="sxs-lookup"><span data-stu-id="d8917-427">[Debugging Structures](debugging-structures.md)\\</span></span>
