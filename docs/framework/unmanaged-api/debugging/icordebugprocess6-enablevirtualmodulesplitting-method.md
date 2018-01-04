---
title: "ICorDebugProcess6::EnableVirtualModuleSplitting 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34a2c2571ba7f3560d861d0a5271cc3a955253a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a><span data-ttu-id="b917c-102">ICorDebugProcess6::EnableVirtualModuleSplitting 方法</span><span class="sxs-lookup"><span data-stu-id="b917c-102">ICorDebugProcess6::EnableVirtualModuleSplitting Method</span></span>
<span data-ttu-id="b917c-103">启用或禁用虚拟模块拆分。</span><span class="sxs-lookup"><span data-stu-id="b917c-103">Enables or disables virtual module splitting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b917c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b917c-104">Syntax</span></span>  
  
```  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b917c-105">参数</span><span class="sxs-lookup"><span data-stu-id="b917c-105">Parameters</span></span>  
 `enableSplitting`  
 <span data-ttu-id="b917c-106">`true` 来启用虚拟模块拆分；`false` 来将其禁用。</span><span class="sxs-lookup"><span data-stu-id="b917c-106">`true` to enable virtual module splitting; `false` to disable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b917c-107">备注</span><span class="sxs-lookup"><span data-stu-id="b917c-107">Remarks</span></span>  
 <span data-ttu-id="b917c-108">虚拟模块拆分导致[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)识别生成过程合并到一起的模块处理并将它们呈现为一组单独模块而非单独的大模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-108">Virtual module splitting causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) to recognize modules that were merged together during the build process and present them as a group of separate modules rather than a single large module.</span></span> <span data-ttu-id="b917c-109">执行此操作更改的各种行为[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)如下所述的方法。</span><span class="sxs-lookup"><span data-stu-id="b917c-109">Doing this changes the behavior of various [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods described below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b917c-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b917c-110">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="b917c-111">可随时调用方法并更改 `enableSplitting` 值。</span><span class="sxs-lookup"><span data-stu-id="b917c-111">This method can be called and the value of `enableSplitting` can be changed at any time.</span></span> <span data-ttu-id="b917c-112">它不会导致任何状态功能变化[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象，而非更改中列出的方法的行为[虚拟模块拆分和未托管调试 Api](#APIs)在调用它们的时间部分。</span><span class="sxs-lookup"><span data-stu-id="b917c-112">It does not cause any stateful functional changes in an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object, other than altering the behavior of the methods listed in the [Virtual module splitting and the unmanaged debugging APIs](#APIs) section at the time they are called.</span></span> <span data-ttu-id="b917c-113">调用那些方法时，使用虚拟模块确实会导致性能显著下降。</span><span class="sxs-lookup"><span data-stu-id="b917c-113">Using virtual modules does incur a performance penalty when calling those methods.</span></span> <span data-ttu-id="b917c-114">此外，重要的内存中缓存的虚拟化的元数据可能需要正确实现[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)可能保留 Api 和这些缓存，即使虚拟模块拆分已关闭。</span><span class="sxs-lookup"><span data-stu-id="b917c-114">In addition, significant in-memory caching of the virtualized metadata may be required to correctly implement the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) APIs, and these caches may be retained even after virtual module splitting has been turned off.</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="b917c-115">术语</span><span class="sxs-lookup"><span data-stu-id="b917c-115">Terminology</span></span>  
 <span data-ttu-id="b917c-116">描述虚拟模块拆分时会用到下列术语：</span><span class="sxs-lookup"><span data-stu-id="b917c-116">The following terms are used when describing virtual module splitting:</span></span>  
  
 <span data-ttu-id="b917c-117">容器模块，即容器</span><span class="sxs-lookup"><span data-stu-id="b917c-117">container modules, or containers</span></span>  
 <span data-ttu-id="b917c-118">聚合模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-118">The aggregate modules.</span></span>  
  
 <span data-ttu-id="b917c-119">子模块，即虚拟模块</span><span class="sxs-lookup"><span data-stu-id="b917c-119">sub-modules, or virtual modules</span></span>  
 <span data-ttu-id="b917c-120">在容器中发现的各模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-120">The modules found in a container.</span></span>  
  
 <span data-ttu-id="b917c-121">普通模块</span><span class="sxs-lookup"><span data-stu-id="b917c-121">regular modules</span></span>  
 <span data-ttu-id="b917c-122">未在生成过程中合并的模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-122">Modules that were not merged at build time.</span></span> <span data-ttu-id="b917c-123">它们既不是容器模块也不是子模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-123">They are neither container modules nor sub-modules.</span></span>  
  
 <span data-ttu-id="b917c-124">ICorDebugModule 接口对象由表示容器模块和子模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-124">Both container modules and sub-modules are represented by ICorDebugModule interface objects.</span></span> <span data-ttu-id="b917c-125">但是，该接口的行为是略有不同每种情况下，作为\<x-引用部分 > 部分介绍。</span><span class="sxs-lookup"><span data-stu-id="b917c-125">However, the behavior of the interface is slightly different in each case, as the \<x-ref to section> section describes.</span></span>  
  
## <a name="modules-and-assemblies"></a><span data-ttu-id="b917c-126">模块和程序集</span><span class="sxs-lookup"><span data-stu-id="b917c-126">Modules and assemblies</span></span>  
 <span data-ttu-id="b917c-127">在程序集合并的情况下，多模块程序集不受支持，因此模块和程序集之间存在一对一的关系。</span><span class="sxs-lookup"><span data-stu-id="b917c-127">Multi-module assemblies are not supported for assembly merging scenarios, so there is a one-to-one relationship between a module and an assembly.</span></span> <span data-ttu-id="b917c-128">每个 icor 调试模块对象，不论其代表容器模块还是子模块中，有一个相应的 icor 调试程序集对象。</span><span class="sxs-lookup"><span data-stu-id="b917c-128">Each ICorDebugModule object, regardless of whether it represents a container module or a sub-module, has a corresponding ICorDebugAssembly object.</span></span> <span data-ttu-id="b917c-129">[:: Getassembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)方法从模块转换为程序集。</span><span class="sxs-lookup"><span data-stu-id="b917c-129">The [ICorDebugModule::GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) method converts from the module to the assembly.</span></span> <span data-ttu-id="b917c-130">若要在另一个方向，将映射[icordebugassembly:: Enumeratemodules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)方法枚举只有 1 个模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-130">To map in the other direction, the [ICorDebugAssembly::EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) method enumerates only 1 module.</span></span> <span data-ttu-id="b917c-131">因为在此情况下的程序集和模块形成了一个紧密耦合对，术语程序集和模块变得在很大程度上可以互换。</span><span class="sxs-lookup"><span data-stu-id="b917c-131">Because assembly and module form a tightly coupled pair in this case, the terms assembly and module become largely interchangeable.</span></span>  
  
## <a name="behavioral-differences"></a><span data-ttu-id="b917c-132">行为差异</span><span class="sxs-lookup"><span data-stu-id="b917c-132">Behavioral differences</span></span>  
 <span data-ttu-id="b917c-133">容器模块包含以下行为和特征：</span><span class="sxs-lookup"><span data-stu-id="b917c-133">Container modules have the following behaviors and characteristics:</span></span>  
  
-   <span data-ttu-id="b917c-134">所有组成子模块的元数据合并在一起。</span><span class="sxs-lookup"><span data-stu-id="b917c-134">Their metadata for all of the constituent sub-modules is merged together.</span></span>  
  
-   <span data-ttu-id="b917c-135">类型名称可能改变。</span><span class="sxs-lookup"><span data-stu-id="b917c-135">Their type names may be mangled.</span></span>  
  
-   <span data-ttu-id="b917c-136">[Icordebugmodule:: Getname](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)方法将路径返回到存在磁盘上的模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-136">The [ICorDebugModule::GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) method returns the path to an on-disk module.</span></span>  
  
-   <span data-ttu-id="b917c-137">[Icordebugmodule:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)方法返回相应图像大小。</span><span class="sxs-lookup"><span data-stu-id="b917c-137">The [ICorDebugModule::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) method returns the size of that image.</span></span>  
  
-   <span data-ttu-id="b917c-138">ICorDebugAssembly3.EnumerateContainedAssemblies 方法列举子模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-138">The ICorDebugAssembly3.EnumerateContainedAssemblies method lists the sub-modules.</span></span>  
  
-   <span data-ttu-id="b917c-139">ICorDebugAssembly3.GetContainerAssembly 方法返回 `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="b917c-139">The ICorDebugAssembly3.GetContainerAssembly method returns `S_FALSE`.</span></span>  
  
 <span data-ttu-id="b917c-140">子模块包含以下行为和特征：</span><span class="sxs-lookup"><span data-stu-id="b917c-140">Sub-modules have the following behaviors and characteristics:</span></span>  
  
-   <span data-ttu-id="b917c-141">他们具有一套减少的元数据，这些元数据只对应合并的原始程序集。</span><span class="sxs-lookup"><span data-stu-id="b917c-141">They have a reduced set of metadata that corresponds only to the original assembly that was merged.</span></span>  
  
-   <span data-ttu-id="b917c-142">元数据名未改变。</span><span class="sxs-lookup"><span data-stu-id="b917c-142">The metadata names are not mangled.</span></span>  
  
-   <span data-ttu-id="b917c-143">元数据令牌经生成过程合并之前，不大可能与原始程序集中的令牌匹配。</span><span class="sxs-lookup"><span data-stu-id="b917c-143">Metadata tokens are unlikely to match the tokens in the original assembly before it was merged in the build process.</span></span>  
  
-   <span data-ttu-id="b917c-144">[Icordebugmodule:: Getname](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)方法返回程序集名而不是文件路径。</span><span class="sxs-lookup"><span data-stu-id="b917c-144">The [ICorDebugModule::GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) method returns the assembly name, not a file path.</span></span>  
  
-   <span data-ttu-id="b917c-145">[Icordebugmodule:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)方法返回原始的未合并的映像大小。</span><span class="sxs-lookup"><span data-stu-id="b917c-145">The [ICorDebugModule::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) method returns the original unmerged image size.</span></span>  
  
-   <span data-ttu-id="b917c-146">ICorDebugModule3.EnumerateContainedAssemblies 方法返回 `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="b917c-146">The ICorDebugModule3.EnumerateContainedAssemblies method returns `S_FALSE`.</span></span>  
  
-   <span data-ttu-id="b917c-147">ICorDebugAssembly3.GetContainerAssembly 方法返回包含模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-147">The ICorDebugAssembly3.GetContainerAssembly method returns the containing module.</span></span>  
  
## <a name="interfaces-retrieved-from-modules"></a><span data-ttu-id="b917c-148">从模块恢复的接口</span><span class="sxs-lookup"><span data-stu-id="b917c-148">Interfaces retrieved from modules</span></span>  
 <span data-ttu-id="b917c-149">模块可恢复或创建多个接口。</span><span class="sxs-lookup"><span data-stu-id="b917c-149">A variety of interfaces can be created or retrieved from modules.</span></span> <span data-ttu-id="b917c-150">其中包括：</span><span class="sxs-lookup"><span data-stu-id="b917c-150">Some of these include:</span></span>  
  
-   <span data-ttu-id="b917c-151">一个 ICorDebugClass 对象，它返回[icordebugmodule:: Getclassfromtoken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b917c-151">An ICorDebugClass object, which is returned by the [ICorDebugModule::GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) method.</span></span>  
  
-   <span data-ttu-id="b917c-152">一个 icor 调试程序集对象，它返回[:: Getassembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b917c-152">An ICorDebugAssembly object, which is returned by the [ICorDebugModule::GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) method.</span></span>  
  
 <span data-ttu-id="b917c-153">这些对象始终由缓存[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)，并且它们将具有相同的指针标识，无论它们已创建还是从容器模块还是子模块查询。</span><span class="sxs-lookup"><span data-stu-id="b917c-153">These objects are always cached by [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), and they will have the same pointer identity regardless of whether they were created or queried from the container module or a sub-module.</span></span> <span data-ttu-id="b917c-154">子模块提供了这些缓存对象的筛选视图，而非包含各自副本的单独缓存。</span><span class="sxs-lookup"><span data-stu-id="b917c-154">The sub-module provides a filtered view of these cached objects, not a separate cache with its own copies.</span></span>  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a><span data-ttu-id="b917c-155">虚拟模块拆分和未托管调试 API</span><span class="sxs-lookup"><span data-stu-id="b917c-155">Virtual module splitting and the unmanaged debugging APIs</span></span>  
 <span data-ttu-id="b917c-156">下表显示了虚拟模块拆分如何影响未托管调试 API 中的其他方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b917c-156">The following table shows how virtual module splitting affects the behavior of other methods in the unmanaged debugging API.</span></span>  
  
|<span data-ttu-id="b917c-157">方法</span><span class="sxs-lookup"><span data-stu-id="b917c-157">Method</span></span>|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[<span data-ttu-id="b917c-158">Icordebugfunction:: Getmodule</span><span class="sxs-lookup"><span data-stu-id="b917c-158">ICorDebugFunction::GetModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="b917c-159">返回最初定义该功能的子模块</span><span class="sxs-lookup"><span data-stu-id="b917c-159">Returns the sub-module this function was originally defined in</span></span>|<span data-ttu-id="b917c-160">返回该功能合并到的容器模块</span><span class="sxs-lookup"><span data-stu-id="b917c-160">Returns the container module this function was merged into</span></span>|  
|[<span data-ttu-id="b917c-161">Icordebugclass:: Getmodule</span><span class="sxs-lookup"><span data-stu-id="b917c-161">ICorDebugClass::GetModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="b917c-162">返回最初定义该类的子模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-162">Returns the sub-module this class was originally defined in.</span></span>|<span data-ttu-id="b917c-163">返回该类合并到的容器模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-163">Returns the container module this class was merged into.</span></span>|  
|<span data-ttu-id="b917c-164">ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="b917c-164">ICorDebugModuleDebugEvent::GetModule</span></span>|<span data-ttu-id="b917c-165">返回加载的容器模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-165">Returns the container module that was loaded.</span></span> <span data-ttu-id="b917c-166">不管此设置如何，子模块不会收到加载事件。</span><span class="sxs-lookup"><span data-stu-id="b917c-166">Sub-modules are not given load events regardless of this setting.</span></span>|<span data-ttu-id="b917c-167">返回加载的容器模块。</span><span class="sxs-lookup"><span data-stu-id="b917c-167">Returns the container module that was loaded.</span></span>|  
|[<span data-ttu-id="b917c-168">Icordebugappdomain:: Enumerateassemblies</span><span class="sxs-lookup"><span data-stu-id="b917c-168">ICorDebugAppDomain::EnumerateAssemblies</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="b917c-169">返回一组子程序集和普通程序集；不包含容器程序集。</span><span class="sxs-lookup"><span data-stu-id="b917c-169">Returns a list of sub-assemblies and regular assemblies; no container assemblies are included.</span></span> <span data-ttu-id="b917c-170">**注意：**如果任一容器程序集缺少符号，将枚举其子程序集组成。</span><span class="sxs-lookup"><span data-stu-id="b917c-170">**Note:**  If any container assembly is missing symbols, none of its sub-assemblies will be enumerated.</span></span> <span data-ttu-id="b917c-171">如果任一普通程序集缺少符号，则其可能被枚举或不枚举。</span><span class="sxs-lookup"><span data-stu-id="b917c-171">If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|<span data-ttu-id="b917c-172">返回一组子程序集和普通程序集；不包含子程序集。</span><span class="sxs-lookup"><span data-stu-id="b917c-172">Returns a list of container assemblies and regular assemblies; no sub-assemblies are included.</span></span> <span data-ttu-id="b917c-173">**注意：**如果任一普通程序集缺少符号，则它可能或可能不枚举。</span><span class="sxs-lookup"><span data-stu-id="b917c-173">**Note:**  If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|  
|<span data-ttu-id="b917c-174">[Icordebugcode::](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) （当只指向 IL 代码的引用）</span><span class="sxs-lookup"><span data-stu-id="b917c-174">[ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (when referring to IL code only)</span></span>|<span data-ttu-id="b917c-175">返回可能在预合并程序集图像中有效的 IL。</span><span class="sxs-lookup"><span data-stu-id="b917c-175">Returns IL that would be valid in a pre-merge assembly image.</span></span> <span data-ttu-id="b917c-176">具体来说，当包含 IL 的虚拟模块未定义参考类型时，任一内联元数据令牌都可以作为 TypeRef 或 MemberRef 令牌。</span><span class="sxs-lookup"><span data-stu-id="b917c-176">Specifically, any inline metadata tokens will correctly be TypeRef or MemberRef tokens when the types being referred to are not defined in the virtual module containing the IL.</span></span> <span data-ttu-id="b917c-177">可以在中查找这些 TypeRef 或 MemberRef 令牌[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)相应虚拟 icor 调试模块对象的对象。</span><span class="sxs-lookup"><span data-stu-id="b917c-177">These TypeRef or MemberRef tokens can be looked up in the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object for the corresponding virtual ICorDebugModule object.</span></span>|<span data-ttu-id="b917c-178">返回预合并程序集图像中的 IL。</span><span class="sxs-lookup"><span data-stu-id="b917c-178">Returns the IL in the post-merge assembly image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b917c-179">惠?</span><span class="sxs-lookup"><span data-stu-id="b917c-179">Requirements</span></span>  
 <span data-ttu-id="b917c-180">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b917c-180">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b917c-181">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b917c-181">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b917c-182">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b917c-182">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b917c-183">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b917c-183">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b917c-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="b917c-184">See Also</span></span>  
 [<span data-ttu-id="b917c-185">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="b917c-185">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="b917c-186">调试接口</span><span class="sxs-lookup"><span data-stu-id="b917c-186">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
