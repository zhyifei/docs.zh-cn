---
title: ICorDebugProcess6::EnableVirtualModuleSplitting 方法
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 8ad15d11ce81323b30434b3db98259a74a198f29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178562"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a><span data-ttu-id="b2aee-102">ICorDebugProcess6::EnableVirtualModuleSplitting 方法</span><span class="sxs-lookup"><span data-stu-id="b2aee-102">ICorDebugProcess6::EnableVirtualModuleSplitting Method</span></span>
<span data-ttu-id="b2aee-103">启用或禁用虚拟模块拆分。</span><span class="sxs-lookup"><span data-stu-id="b2aee-103">Enables or disables virtual module splitting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2aee-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2aee-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2aee-105">parameters</span><span class="sxs-lookup"><span data-stu-id="b2aee-105">Parameters</span></span>  
 `enableSplitting`  
 <span data-ttu-id="b2aee-106">`true` 来启用虚拟模块拆分；`false` 来将其禁用。</span><span class="sxs-lookup"><span data-stu-id="b2aee-106">`true` to enable virtual module splitting; `false` to disable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2aee-107">备注</span><span class="sxs-lookup"><span data-stu-id="b2aee-107">Remarks</span></span>  
 <span data-ttu-id="b2aee-108">虚拟模块拆分导致[ICorDebug](icordebug-interface.md)识别在生成过程中合并在一起的模块，并将其作为一组单独的模块而不是单个大型模块呈现。</span><span class="sxs-lookup"><span data-stu-id="b2aee-108">Virtual module splitting causes [ICorDebug](icordebug-interface.md) to recognize modules that were merged together during the build process and present them as a group of separate modules rather than a single large module.</span></span> <span data-ttu-id="b2aee-109">这样做会更改下面描述的各种[ICorDebug](icordebug-interface.md)方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b2aee-109">Doing this changes the behavior of various [ICorDebug](icordebug-interface.md) methods described below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2aee-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b2aee-110">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="b2aee-111">可随时调用方法并更改 `enableSplitting` 值。</span><span class="sxs-lookup"><span data-stu-id="b2aee-111">This method can be called and the value of `enableSplitting` can be changed at any time.</span></span> <span data-ttu-id="b2aee-112">它不会在[ICorDebug](icordebug-interface.md)对象中导致任何有状态的功能更改，除了更改[调用虚拟模块拆分和非托管调试 API](#APIs)部分中列出的方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b2aee-112">It does not cause any stateful functional changes in an [ICorDebug](icordebug-interface.md) object, other than altering the behavior of the methods listed in the [Virtual module splitting and the unmanaged debugging APIs](#APIs) section at the time they are called.</span></span> <span data-ttu-id="b2aee-113">调用那些方法时，使用虚拟模块确实会导致性能显著下降。</span><span class="sxs-lookup"><span data-stu-id="b2aee-113">Using virtual modules does incur a performance penalty when calling those methods.</span></span> <span data-ttu-id="b2aee-114">此外，可能需要大量虚拟化元数据的内存缓存才能正确实现[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) API，即使在关闭虚拟模块拆分后，这些缓存也可能保留。</span><span class="sxs-lookup"><span data-stu-id="b2aee-114">In addition, significant in-memory caching of the virtualized metadata may be required to correctly implement the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) APIs, and these caches may be retained even after virtual module splitting has been turned off.</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="b2aee-115">术语</span><span class="sxs-lookup"><span data-stu-id="b2aee-115">Terminology</span></span>  
 <span data-ttu-id="b2aee-116">描述虚拟模块拆分时会用到下列术语：</span><span class="sxs-lookup"><span data-stu-id="b2aee-116">The following terms are used when describing virtual module splitting:</span></span>  
  
 <span data-ttu-id="b2aee-117">容器模块，即容器</span><span class="sxs-lookup"><span data-stu-id="b2aee-117">container modules, or containers</span></span>  
 <span data-ttu-id="b2aee-118">聚合模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-118">The aggregate modules.</span></span>  
  
 <span data-ttu-id="b2aee-119">子模块，即虚拟模块</span><span class="sxs-lookup"><span data-stu-id="b2aee-119">sub-modules, or virtual modules</span></span>  
 <span data-ttu-id="b2aee-120">在容器中发现的各模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-120">The modules found in a container.</span></span>  
  
 <span data-ttu-id="b2aee-121">普通模块</span><span class="sxs-lookup"><span data-stu-id="b2aee-121">regular modules</span></span>  
 <span data-ttu-id="b2aee-122">未在生成过程中合并的模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-122">Modules that were not merged at build time.</span></span> <span data-ttu-id="b2aee-123">它们既不是容器模块也不是子模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-123">They are neither container modules nor sub-modules.</span></span>  
  
 <span data-ttu-id="b2aee-124">但 ICor调试模块接口对象会表示容器模块和子模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-124">Both container modules and sub-modules are represented by ICorDebugModule interface objects.</span></span> <span data-ttu-id="b2aee-125">但是，接口的行为在每种情况下都略有不同，如第>节的\<xref 描述。</span><span class="sxs-lookup"><span data-stu-id="b2aee-125">However, the behavior of the interface is slightly different in each case, as the \<x-ref to section> section describes.</span></span>  
  
## <a name="modules-and-assemblies"></a><span data-ttu-id="b2aee-126">模块和程序集</span><span class="sxs-lookup"><span data-stu-id="b2aee-126">Modules and assemblies</span></span>  
 <span data-ttu-id="b2aee-127">在程序集合并的情况下，多模块程序集不受支持，因此模块和程序集之间存在一对一的关系。</span><span class="sxs-lookup"><span data-stu-id="b2aee-127">Multi-module assemblies are not supported for assembly merging scenarios, so there is a one-to-one relationship between a module and an assembly.</span></span> <span data-ttu-id="b2aee-128">每个 ICor调试模块对象（不论其代表容器模块还是子模块）都拥有相应的 ICor调试程序集对象。</span><span class="sxs-lookup"><span data-stu-id="b2aee-128">Each ICorDebugModule object, regardless of whether it represents a container module or a sub-module, has a corresponding ICorDebugAssembly object.</span></span> <span data-ttu-id="b2aee-129">[ICorDebugModule：获取组装](icordebugmodule-getassembly-method.md)方法从模块转换为程序集。</span><span class="sxs-lookup"><span data-stu-id="b2aee-129">The [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method converts from the module to the assembly.</span></span> <span data-ttu-id="b2aee-130">要向其他方向映射[，ICorDebugAssembly：：枚举模块](icordebugassembly-enumeratemodules-method.md)方法仅枚举 1 个模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-130">To map in the other direction, the [ICorDebugAssembly::EnumerateModules](icordebugassembly-enumeratemodules-method.md) method enumerates only 1 module.</span></span> <span data-ttu-id="b2aee-131">因为在此情况下的程序集和模块形成了一个紧密耦合对，术语程序集和模块变得在很大程度上可以互换。</span><span class="sxs-lookup"><span data-stu-id="b2aee-131">Because assembly and module form a tightly coupled pair in this case, the terms assembly and module become largely interchangeable.</span></span>  
  
## <a name="behavioral-differences"></a><span data-ttu-id="b2aee-132">行为差异</span><span class="sxs-lookup"><span data-stu-id="b2aee-132">Behavioral differences</span></span>  
 <span data-ttu-id="b2aee-133">容器模块包含以下行为和特征：</span><span class="sxs-lookup"><span data-stu-id="b2aee-133">Container modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="b2aee-134">所有组成子模块的元数据合并在一起。</span><span class="sxs-lookup"><span data-stu-id="b2aee-134">Their metadata for all of the constituent sub-modules is merged together.</span></span>  
  
- <span data-ttu-id="b2aee-135">类型名称可能改变。</span><span class="sxs-lookup"><span data-stu-id="b2aee-135">Their type names may be mangled.</span></span>  
  
- <span data-ttu-id="b2aee-136">[ICorDebugModule：：GetName](icordebugmodule-getname-method.md)方法返回磁盘模块的路径。</span><span class="sxs-lookup"><span data-stu-id="b2aee-136">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the path to an on-disk module.</span></span>  
  
- <span data-ttu-id="b2aee-137">[ICorDebugModule：GetSize](icordebugmodule-getsize-method.md)方法返回该图像的大小。</span><span class="sxs-lookup"><span data-stu-id="b2aee-137">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the size of that image.</span></span>  
  
- <span data-ttu-id="b2aee-138">ICorDebugAssembly3.EnumerateContainedAssemblies 方法列举子模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-138">The ICorDebugAssembly3.EnumerateContainedAssemblies method lists the sub-modules.</span></span>  
  
- <span data-ttu-id="b2aee-139">ICorDebugAssembly3.GetContainerAssembly 方法返回 `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="b2aee-139">The ICorDebugAssembly3.GetContainerAssembly method returns `S_FALSE`.</span></span>  
  
 <span data-ttu-id="b2aee-140">子模块包含以下行为和特征：</span><span class="sxs-lookup"><span data-stu-id="b2aee-140">Sub-modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="b2aee-141">他们具有一套减少的元数据，这些元数据只对应合并的原始程序集。</span><span class="sxs-lookup"><span data-stu-id="b2aee-141">They have a reduced set of metadata that corresponds only to the original assembly that was merged.</span></span>  
  
- <span data-ttu-id="b2aee-142">元数据名未改变。</span><span class="sxs-lookup"><span data-stu-id="b2aee-142">The metadata names are not mangled.</span></span>  
  
- <span data-ttu-id="b2aee-143">元数据令牌经生成过程合并之前，不大可能与原始程序集中的令牌匹配。</span><span class="sxs-lookup"><span data-stu-id="b2aee-143">Metadata tokens are unlikely to match the tokens in the original assembly before it was merged in the build process.</span></span>  
  
- <span data-ttu-id="b2aee-144">[ICorDebugModule：getName](icordebugmodule-getname-method.md)方法返回程序集名称，而不是文件路径。</span><span class="sxs-lookup"><span data-stu-id="b2aee-144">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the assembly name, not a file path.</span></span>  
  
- <span data-ttu-id="b2aee-145">[ICorDebugModule：GetSize](icordebugmodule-getsize-method.md)方法返回原始未合并的图像大小。</span><span class="sxs-lookup"><span data-stu-id="b2aee-145">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the original unmerged image size.</span></span>  
  
- <span data-ttu-id="b2aee-146">ICorDebugModule3.EnumerateContainedAssemblies 方法返回 `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="b2aee-146">The ICorDebugModule3.EnumerateContainedAssemblies method returns `S_FALSE`.</span></span>  
  
- <span data-ttu-id="b2aee-147">ICorDebugAssembly3.GetContainerAssembly 方法返回包含模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-147">The ICorDebugAssembly3.GetContainerAssembly method returns the containing module.</span></span>  
  
## <a name="interfaces-retrieved-from-modules"></a><span data-ttu-id="b2aee-148">从模块恢复的接口</span><span class="sxs-lookup"><span data-stu-id="b2aee-148">Interfaces retrieved from modules</span></span>  
 <span data-ttu-id="b2aee-149">模块可恢复或创建多个接口。</span><span class="sxs-lookup"><span data-stu-id="b2aee-149">A variety of interfaces can be created or retrieved from modules.</span></span> <span data-ttu-id="b2aee-150">其中包括：</span><span class="sxs-lookup"><span data-stu-id="b2aee-150">Some of these include:</span></span>  
  
- <span data-ttu-id="b2aee-151">ICorDebugClass 对象，由[ICorDebugModule 返回：：获取ClassFromToken](icordebugmodule-getclassfromtoken-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b2aee-151">An ICorDebugClass object, which is returned by the [ICorDebugModule::GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) method.</span></span>  
  
- <span data-ttu-id="b2aee-152">ICorDebugAssembly 对象，由[ICorDebugModule：getAssembly](icordebugmodule-getassembly-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="b2aee-152">An ICorDebugAssembly object, which is returned by the [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method.</span></span>  
  
 <span data-ttu-id="b2aee-153">这些对象始终由[ICorDebug](icordebug-interface.md)缓存，无论它们是从容器模块还是子模块创建还是查询它们，它们都将具有相同的指针标识。</span><span class="sxs-lookup"><span data-stu-id="b2aee-153">These objects are always cached by [ICorDebug](icordebug-interface.md), and they will have the same pointer identity regardless of whether they were created or queried from the container module or a sub-module.</span></span> <span data-ttu-id="b2aee-154">子模块提供了这些缓存对象的筛选视图，而非包含各自副本的单独缓存。</span><span class="sxs-lookup"><span data-stu-id="b2aee-154">The sub-module provides a filtered view of these cached objects, not a separate cache with its own copies.</span></span>  
  
<a name="APIs"></a>
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a><span data-ttu-id="b2aee-155">虚拟模块拆分和未托管调试 API</span><span class="sxs-lookup"><span data-stu-id="b2aee-155">Virtual module splitting and the unmanaged debugging APIs</span></span>  
 <span data-ttu-id="b2aee-156">下表显示了虚拟模块拆分如何影响未托管调试 API 中的其他方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b2aee-156">The following table shows how virtual module splitting affects the behavior of other methods in the unmanaged debugging API.</span></span>  
  
|<span data-ttu-id="b2aee-157">方法</span><span class="sxs-lookup"><span data-stu-id="b2aee-157">Method</span></span>|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[<span data-ttu-id="b2aee-158">ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="b2aee-158">ICorDebugFunction::GetModule</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="b2aee-159">返回最初定义该功能的子模块</span><span class="sxs-lookup"><span data-stu-id="b2aee-159">Returns the sub-module this function was originally defined in</span></span>|<span data-ttu-id="b2aee-160">返回该功能合并到的容器模块</span><span class="sxs-lookup"><span data-stu-id="b2aee-160">Returns the container module this function was merged into</span></span>|  
|[<span data-ttu-id="b2aee-161">ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="b2aee-161">ICorDebugClass::GetModule</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="b2aee-162">返回最初定义该类的子模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-162">Returns the sub-module this class was originally defined in.</span></span>|<span data-ttu-id="b2aee-163">返回该类合并到的容器模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-163">Returns the container module this class was merged into.</span></span>|  
|<span data-ttu-id="b2aee-164">ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="b2aee-164">ICorDebugModuleDebugEvent::GetModule</span></span>|<span data-ttu-id="b2aee-165">返回加载的容器模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-165">Returns the container module that was loaded.</span></span> <span data-ttu-id="b2aee-166">不管此设置如何，子模块不会收到加载事件。</span><span class="sxs-lookup"><span data-stu-id="b2aee-166">Sub-modules are not given load events regardless of this setting.</span></span>|<span data-ttu-id="b2aee-167">返回加载的容器模块。</span><span class="sxs-lookup"><span data-stu-id="b2aee-167">Returns the container module that was loaded.</span></span>|  
|[<span data-ttu-id="b2aee-168">ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="b2aee-168">ICorDebugAppDomain::EnumerateAssemblies</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="b2aee-169">返回一组子程序集和普通程序集；不包含容器程序集。</span><span class="sxs-lookup"><span data-stu-id="b2aee-169">Returns a list of sub-assemblies and regular assemblies; no container assemblies are included.</span></span> <span data-ttu-id="b2aee-170">**注：** 如果缺少任何容器程序集，则不会枚举其任何子程序集。</span><span class="sxs-lookup"><span data-stu-id="b2aee-170">**Note:**  If any container assembly is missing symbols, none of its sub-assemblies will be enumerated.</span></span> <span data-ttu-id="b2aee-171">如果任一普通程序集缺少符号，则其可能被枚举或不枚举。</span><span class="sxs-lookup"><span data-stu-id="b2aee-171">If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|<span data-ttu-id="b2aee-172">返回一组子程序集和普通程序集；不包含子程序集。</span><span class="sxs-lookup"><span data-stu-id="b2aee-172">Returns a list of container assemblies and regular assemblies; no sub-assemblies are included.</span></span> <span data-ttu-id="b2aee-173">**注：** 如果缺少任何常规程序集，则可能会枚举，也可能不枚举。</span><span class="sxs-lookup"><span data-stu-id="b2aee-173">**Note:**  If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|  
|<span data-ttu-id="b2aee-174">[ICorDebug代码：获取代码](icordebugcode-getcode-method.md)（仅参考 IL 代码时）</span><span class="sxs-lookup"><span data-stu-id="b2aee-174">[ICorDebugCode::GetCode](icordebugcode-getcode-method.md) (when referring to IL code only)</span></span>|<span data-ttu-id="b2aee-175">返回可能在预合并程序集图像中有效的 IL。</span><span class="sxs-lookup"><span data-stu-id="b2aee-175">Returns IL that would be valid in a pre-merge assembly image.</span></span> <span data-ttu-id="b2aee-176">具体来说，当包含 IL 的虚拟模块未定义参考类型时，任一内联元数据令牌都可以作为 TypeRef 或 MemberRef 令牌。</span><span class="sxs-lookup"><span data-stu-id="b2aee-176">Specifically, any inline metadata tokens will correctly be TypeRef or MemberRef tokens when the types being referred to are not defined in the virtual module containing the IL.</span></span> <span data-ttu-id="b2aee-177">这些 TypeRef 或成员Ref 令牌可以在[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)对象中为相应的虚拟 ICorDebugModule 对象进行备份。</span><span class="sxs-lookup"><span data-stu-id="b2aee-177">These TypeRef or MemberRef tokens can be looked up in the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object for the corresponding virtual ICorDebugModule object.</span></span>|<span data-ttu-id="b2aee-178">返回预合并程序集图像中的 IL。</span><span class="sxs-lookup"><span data-stu-id="b2aee-178">Returns the IL in the post-merge assembly image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2aee-179">要求</span><span class="sxs-lookup"><span data-stu-id="b2aee-179">Requirements</span></span>  
 <span data-ttu-id="b2aee-180">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2aee-180">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2aee-181">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2aee-181">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2aee-182">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2aee-182">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2aee-183">**.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2aee-183">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2aee-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2aee-184">See also</span></span>

- [<span data-ttu-id="b2aee-185">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="b2aee-185">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="b2aee-186">调试接口</span><span class="sxs-lookup"><span data-stu-id="b2aee-186">Debugging Interfaces</span></span>](debugging-interfaces.md)
