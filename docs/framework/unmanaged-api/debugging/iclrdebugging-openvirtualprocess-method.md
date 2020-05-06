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
ms.openlocfilehash: 1598130eb097655d3e83689956eb3614103eb573
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860379"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="ecbd5-102">ICLRDebugging::OpenVirtualProcess 方法</span><span class="sxs-lookup"><span data-stu-id="ecbd5-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="ecbd5-103">获取与进程中加载的公共语言运行时（CLR）模块相对应的 ICorDebugProcess 接口。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbd5-104">语法</span><span class="sxs-lookup"><span data-stu-id="ecbd5-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ecbd5-105">参数</span><span class="sxs-lookup"><span data-stu-id="ecbd5-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="ecbd5-106">中目标进程中的模块的基址。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="ecbd5-107">如果指定的模块不是 CLR 模块，则将返回 COR_E_NOT_CLR。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="ecbd5-108">中一种数据目标抽象，允许托管调试器检查进程状态。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="ecbd5-109">调试器必须实现[ICorDebugDataTarget](icordebugdatatarget-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-109">The debugger must implement the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="ecbd5-110">应该实现[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)接口以支持在计算机上未本地安装正在调试的 CLR 的情况。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-110">You should implement the [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="ecbd5-111">中一种库提供程序回调接口，允许根据需要定位和加载特定于版本的调试库。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="ecbd5-112">仅当`ppProcess`或`pFlags`不`null`为时，才需要此参数。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="ecbd5-113">中此调试器可以调试的 CLR 的最高版本。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="ecbd5-114">你应从该调试器支持的最新 CLR 版本中指定主版本、次版本和内部版本，并将修订号设置为65535，以适应未来的就地 CLR 服务版本。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="ecbd5-115">中要检索的 ICorDebugProcess 接口的 ID。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="ecbd5-116">目前，唯一接受的值是 IID_CORDEBUGPROCESS3、IID_CORDEBUGPROCESS2 和 IID_CORDEBUGPROCESS。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="ecbd5-117">弄指向由标识的 COM 接口的指针`riidProcess`。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="ecbd5-118">[in，out]CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="ecbd5-119">对于输入，此值可以为`null`。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-119">On input, this value can be `null`.</span></span> <span data-ttu-id="ecbd5-120">它还可以指向[CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md)结构，在这种情况下，结构的`wStructVersion`字段必须初始化为0（零）。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-120">It can also point to a [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="ecbd5-121">输出时，将用`CLR_DEBUGGING_VERSION` CLR 的版本信息填充返回的结构。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="ecbd5-122">弄有关指定运行时的信息性标志。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="ecbd5-123">有关标志的说明，请参阅[CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md)主题。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecbd5-124">返回值</span><span class="sxs-lookup"><span data-stu-id="ecbd5-124">Return Value</span></span>  
 <span data-ttu-id="ecbd5-125">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ecbd5-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecbd5-126">HRESULT</span></span>|<span data-ttu-id="ecbd5-127">说明</span><span class="sxs-lookup"><span data-stu-id="ecbd5-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ecbd5-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecbd5-128">S_OK</span></span>|<span data-ttu-id="ecbd5-129">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="ecbd5-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ecbd5-130">E_POINTER</span></span>|<span data-ttu-id="ecbd5-131">`pDataTarget` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="ecbd5-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="ecbd5-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="ecbd5-133">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)回调返回错误或未提供有效的句柄。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-133">The [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="ecbd5-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="ecbd5-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="ecbd5-135">`pDataTarget`对于此版本的运行时，不实现所需的数据目标接口。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="ecbd5-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="ecbd5-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="ecbd5-137">指示的模块不是 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="ecbd5-138">当由于内存已损坏、该模块不可用或 CLR 版本高于填充码版本而无法检测到 CLR 模块时，也会返回此 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="ecbd5-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="ecbd5-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="ecbd5-140">此运行时版本不支持此调试模型。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="ecbd5-141">目前，CLR 版本在 .NET Framework 4 之前不支持调试模型。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="ecbd5-142">此`pwszVersion`错误后，output 参数仍设置为正确的值。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="ecbd5-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="ecbd5-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="ecbd5-144">CLR 的版本高于此调试器支持的版本。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="ecbd5-145">此`pwszVersion`错误后，output 参数仍设置为正确的值。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="ecbd5-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="ecbd5-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="ecbd5-147">`riidProcess`接口不可用。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="ecbd5-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="ecbd5-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="ecbd5-149">`CLR_DEBUGGING_VERSION`结构没有可识别的值`wStructVersion`。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="ecbd5-150">此时唯一接受的值为0。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ecbd5-151">异常</span><span class="sxs-lookup"><span data-stu-id="ecbd5-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecbd5-152">备注</span><span class="sxs-lookup"><span data-stu-id="ecbd5-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbd5-153">要求</span><span class="sxs-lookup"><span data-stu-id="ecbd5-153">Requirements</span></span>  
 <span data-ttu-id="ecbd5-154">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbd5-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbd5-155">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecbd5-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecbd5-156">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecbd5-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecbd5-157">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecbd5-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbd5-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecbd5-158">See also</span></span>

- [<span data-ttu-id="ecbd5-159">调试接口</span><span class="sxs-lookup"><span data-stu-id="ecbd5-159">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ecbd5-160">调试</span><span class="sxs-lookup"><span data-stu-id="ecbd5-160">Debugging</span></span>](index.md)
