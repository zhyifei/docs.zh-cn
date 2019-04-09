---
title: ICLRDebugging::OpenVirtualProcess 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a313ea62455067fb36b94d942b0ce21589677e3b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122572"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="9f6ea-102">ICLRDebugging::OpenVirtualProcess 方法</span><span class="sxs-lookup"><span data-stu-id="9f6ea-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="9f6ea-103">获取对应于在进程中加载了公共语言运行时 (CLR) 模块的 ICorDebugProcess 接口。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f6ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f6ea-104">Syntax</span></span>  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f6ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f6ea-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="9f6ea-106">[in]目标进程中的模块基址。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="9f6ea-107">如果指定的模块不是 CLR 模块，将返回 COR_E_NOT_CLR。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="9f6ea-108">[in]数据目标抽象，让托管的调试器要检查进程状态。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="9f6ea-109">调试器必须实现[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="9f6ea-110">应实现[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)接口以支持方案的 CLR 正在调试的是本地计算机未安装。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="9f6ea-111">[in]允许特定于版本的调试库，根据需要定位和加载上一个库提供程序回调接口。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="9f6ea-112">此参数是必需的仅当`ppProcess`或`pFlags`不是`null`。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="9f6ea-113">[in]此调试器可以调试 CLR 最高版本。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="9f6ea-114">应指定主要、 次要和内部版本的最新的 CLR 版本，此调试器支持，并设置为 65535 以容纳将来的就地 CLR 服务版本的修订号。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="9f6ea-115">[in]要检索的 ICorDebugProcess 接口 ID。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="9f6ea-116">目前，唯一接受的值为 IID_CORDEBUGPROCESS3、 IID_CORDEBUGPROCESS2 和 IID_CORDEBUGPROCESS。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="9f6ea-117">[out]指向由标识的 COM 接口的指针`riidProcess`。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="9f6ea-118">[in、 out]CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="9f6ea-119">在输入时，此值可以是`null`。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-119">On input, this value can be `null`.</span></span> <span data-ttu-id="9f6ea-120">它也可以指向[CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)结构，这种情况下，该结构的`wStructVersion`字段必须初始化为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="9f6ea-121">在输出时，返回`CLR_DEBUGGING_VERSION`将使用 CLR 的版本信息填充结构。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="9f6ea-122">[out]有关指定的运行时的信息性标志。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="9f6ea-123">请参阅[CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)的标志的说明的主题。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f6ea-124">返回值</span><span class="sxs-lookup"><span data-stu-id="9f6ea-124">Return Value</span></span>  
 <span data-ttu-id="9f6ea-125">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9f6ea-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f6ea-126">HRESULT</span></span>|<span data-ttu-id="9f6ea-127">描述</span><span class="sxs-lookup"><span data-stu-id="9f6ea-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f6ea-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f6ea-128">S_OK</span></span>|<span data-ttu-id="9f6ea-129">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="9f6ea-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9f6ea-130">E_POINTER</span></span>|`pDataTarget` <span data-ttu-id="9f6ea-131">是`null`。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-131">is `null`.</span></span>|  
|<span data-ttu-id="9f6ea-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="9f6ea-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="9f6ea-133">[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)回调返回错误或未提供有效的句柄。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="9f6ea-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="9f6ea-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|`pDataTarget` <span data-ttu-id="9f6ea-135">未实现此版本的运行时所需的数据目标接口。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-135">does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="9f6ea-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="9f6ea-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="9f6ea-137">所指示的模块不是 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="9f6ea-138">不能检测到的 CLR 模块，因为内存损坏、 不可用，该模块或 CLR 版本晚于填充程序版本时，也会返回此 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="9f6ea-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="9f6ea-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="9f6ea-140">此运行时版本不支持此调试模型。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="9f6ea-141">目前，通过以前的 CLR 版本不支持调试模型[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-141">Currently, the debugging model is not supported by CLR versions before the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="9f6ea-142">`pwszVersion`输出参数仍将设置为正确的值后此错误。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="9f6ea-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="9f6ea-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="9f6ea-144">CLR 的版本高于此调试器声明，以便支持的版本。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="9f6ea-145">`pwszVersion`输出参数仍将设置为正确的值后此错误。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="9f6ea-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="9f6ea-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="9f6ea-147">`riidProcess`接口不可用。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="9f6ea-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="9f6ea-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="9f6ea-149">`CLR_DEBUGGING_VERSION`结构不具有可识别的值为`wStructVersion`。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="9f6ea-150">此时唯一接受的值为 0。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9f6ea-151">Exceptions</span><span class="sxs-lookup"><span data-stu-id="9f6ea-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f6ea-152">备注</span><span class="sxs-lookup"><span data-stu-id="9f6ea-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f6ea-153">要求</span><span class="sxs-lookup"><span data-stu-id="9f6ea-153">Requirements</span></span>  
 <span data-ttu-id="9f6ea-154">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f6ea-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f6ea-155">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f6ea-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f6ea-156">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f6ea-156">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9f6ea-157">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="9f6ea-157">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f6ea-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f6ea-158">See also</span></span>

- [<span data-ttu-id="9f6ea-159">调试接口</span><span class="sxs-lookup"><span data-stu-id="9f6ea-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9f6ea-160">调试</span><span class="sxs-lookup"><span data-stu-id="9f6ea-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
