---
title: ICorDebugModule 接口
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dce4f5859568c1288610e171286a5919dc8b19b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962434"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="ed20b-102">ICorDebugModule 接口</span><span class="sxs-lookup"><span data-stu-id="ed20b-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="ed20b-103">表示公共语言运行时 (CLR) 模块, 该模块可以是可执行文件或动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="ed20b-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed20b-104">方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-104">Methods</span></span>  
  
|<span data-ttu-id="ed20b-105">方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-105">Method</span></span>|<span data-ttu-id="ed20b-106">描述</span><span class="sxs-lookup"><span data-stu-id="ed20b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed20b-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="ed20b-108">未实现。</span><span class="sxs-lookup"><span data-stu-id="ed20b-108">Not implemented.</span></span>|  
|[<span data-ttu-id="ed20b-109">EnableClassLoadCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="ed20b-110">确定是否为此模块调用[ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)和[ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="ed20b-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="ed20b-111">EnableJITDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="ed20b-112">确定实时 (JIT) 编译器是否保留此模块内方法的调试信息。</span><span class="sxs-lookup"><span data-stu-id="ed20b-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="ed20b-113">GetAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="ed20b-114">获取包含此模块的程序集。</span><span class="sxs-lookup"><span data-stu-id="ed20b-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="ed20b-115">GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="ed20b-116">获取模块的基址。</span><span class="sxs-lookup"><span data-stu-id="ed20b-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="ed20b-117">GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="ed20b-118">从元数据中获取 ICorDebugClass。</span><span class="sxs-lookup"><span data-stu-id="ed20b-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="ed20b-119">GetEditAndContinueSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="ed20b-120">已否决。</span><span class="sxs-lookup"><span data-stu-id="ed20b-120">Deprecated.</span></span>|  
|[<span data-ttu-id="ed20b-121">GetFunctionFromRVA 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="ed20b-122">未实现。</span><span class="sxs-lookup"><span data-stu-id="ed20b-122">Not implemented.</span></span>|  
|[<span data-ttu-id="ed20b-123">GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="ed20b-124">获取元数据标记指定的函数。</span><span class="sxs-lookup"><span data-stu-id="ed20b-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="ed20b-125">GetGlobalVariableValue 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="ed20b-126">获取指定全局变量的值对象。</span><span class="sxs-lookup"><span data-stu-id="ed20b-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="ed20b-127">GetMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="ed20b-128">获取可用于检查模块的元数据的元数据接口指针。</span><span class="sxs-lookup"><span data-stu-id="ed20b-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="ed20b-129">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="ed20b-130">获取模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="ed20b-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="ed20b-131">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="ed20b-132">获取此模块的包含进程。</span><span class="sxs-lookup"><span data-stu-id="ed20b-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="ed20b-133">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="ed20b-134">获取模块的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ed20b-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="ed20b-135">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="ed20b-136">获取此模块的表项的标记。</span><span class="sxs-lookup"><span data-stu-id="ed20b-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="ed20b-137">IsDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="ed20b-138">指示模块是否为动态模块。</span><span class="sxs-lookup"><span data-stu-id="ed20b-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="ed20b-139">IsInMemory 方法</span><span class="sxs-lookup"><span data-stu-id="ed20b-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="ed20b-140">指示此模块是否仅存在于内存中。</span><span class="sxs-lookup"><span data-stu-id="ed20b-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed20b-141">备注</span><span class="sxs-lookup"><span data-stu-id="ed20b-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed20b-142">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ed20b-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed20b-143">要求</span><span class="sxs-lookup"><span data-stu-id="ed20b-143">Requirements</span></span>  
 <span data-ttu-id="ed20b-144">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed20b-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed20b-145">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="ed20b-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed20b-146">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed20b-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed20b-147">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed20b-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed20b-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed20b-148">See also</span></span>

- [<span data-ttu-id="ed20b-149">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="ed20b-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="ed20b-150">调试接口</span><span class="sxs-lookup"><span data-stu-id="ed20b-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
