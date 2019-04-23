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
ms.openlocfilehash: 257011562a9ea687ef70b842c6d47219283e158e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225633"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="87e4e-102">ICorDebugModule 接口</span><span class="sxs-lookup"><span data-stu-id="87e4e-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="87e4e-103">表示公共语言运行时 (CLR) 模块，这是一个可执行文件或动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="87e4e-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87e4e-104">方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-104">Methods</span></span>  
  
|<span data-ttu-id="87e4e-105">方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-105">Method</span></span>|<span data-ttu-id="87e4e-106">描述</span><span class="sxs-lookup"><span data-stu-id="87e4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87e4e-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="87e4e-108">未实现。</span><span class="sxs-lookup"><span data-stu-id="87e4e-108">Not implemented.</span></span>|  
|[<span data-ttu-id="87e4e-109">EnableClassLoadCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="87e4e-110">确定是否[icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)并[icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)为此模块中调用的回调。</span><span class="sxs-lookup"><span data-stu-id="87e4e-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="87e4e-111">EnableJITDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="87e4e-112">确定在实时 (JIT) 编译器是否保留此模块内方法的调试信息。</span><span class="sxs-lookup"><span data-stu-id="87e4e-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="87e4e-113">GetAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="87e4e-114">获取包含此模块的程序集。</span><span class="sxs-lookup"><span data-stu-id="87e4e-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="87e4e-115">GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="87e4e-116">获取该模块的基址。</span><span class="sxs-lookup"><span data-stu-id="87e4e-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="87e4e-117">GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="87e4e-118">获取 ICorDebugClass 从元数据。</span><span class="sxs-lookup"><span data-stu-id="87e4e-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="87e4e-119">GetEditAndContinueSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="87e4e-120">已否决。</span><span class="sxs-lookup"><span data-stu-id="87e4e-120">Deprecated.</span></span>|  
|[<span data-ttu-id="87e4e-121">GetFunctionFromRVA 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="87e4e-122">未实现。</span><span class="sxs-lookup"><span data-stu-id="87e4e-122">Not implemented.</span></span>|  
|[<span data-ttu-id="87e4e-123">GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="87e4e-124">获取指定的元数据标记的函数。</span><span class="sxs-lookup"><span data-stu-id="87e4e-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="87e4e-125">GetGlobalVariableValue 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="87e4e-126">获取指定的全局变量的值对象。</span><span class="sxs-lookup"><span data-stu-id="87e4e-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="87e4e-127">GetMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="87e4e-128">获取可用于检查该模块的元数据的元数据接口指针。</span><span class="sxs-lookup"><span data-stu-id="87e4e-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="87e4e-129">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="87e4e-130">获取模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="87e4e-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="87e4e-131">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="87e4e-132">获取此模块包含进程。</span><span class="sxs-lookup"><span data-stu-id="87e4e-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="87e4e-133">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="87e4e-134">获取模块的大小以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="87e4e-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="87e4e-135">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="87e4e-136">获取此模块的表项的标记。</span><span class="sxs-lookup"><span data-stu-id="87e4e-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="87e4e-137">IsDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="87e4e-138">指示是否为动态模块。</span><span class="sxs-lookup"><span data-stu-id="87e4e-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="87e4e-139">IsInMemory 方法</span><span class="sxs-lookup"><span data-stu-id="87e4e-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="87e4e-140">指示仅在内存中是否存在此模块。</span><span class="sxs-lookup"><span data-stu-id="87e4e-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87e4e-141">备注</span><span class="sxs-lookup"><span data-stu-id="87e4e-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87e4e-142">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="87e4e-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87e4e-143">要求</span><span class="sxs-lookup"><span data-stu-id="87e4e-143">Requirements</span></span>  
 <span data-ttu-id="87e4e-144">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87e4e-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87e4e-145">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87e4e-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87e4e-146">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87e4e-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87e4e-147">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87e4e-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e4e-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="87e4e-148">See also</span></span>

- [<span data-ttu-id="87e4e-149">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="87e4e-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="87e4e-150">调试接口</span><span class="sxs-lookup"><span data-stu-id="87e4e-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
