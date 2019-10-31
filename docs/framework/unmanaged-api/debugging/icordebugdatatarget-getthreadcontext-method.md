---
title: ICorDebugDataTarget::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 278320391615eddaa8ba878ef87f802f30cddb95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122027"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="f995e-102">ICorDebugDataTarget::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="f995e-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="f995e-103">返回指定线程的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="f995e-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f995e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f995e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f995e-105">参数</span><span class="sxs-lookup"><span data-stu-id="f995e-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="f995e-106">中要检索其上下文的线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="f995e-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="f995e-107">标识符由操作系统定义。</span><span class="sxs-lookup"><span data-stu-id="f995e-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="f995e-108">中平台相关标志的按位组合，用于指示应读取上下文的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="f995e-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f995e-109">[输入] `pContext` 的大小。</span><span class="sxs-lookup"><span data-stu-id="f995e-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="f995e-110">弄将存储线程上下文的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f995e-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f995e-111">备注</span><span class="sxs-lookup"><span data-stu-id="f995e-111">Remarks</span></span>  
 <span data-ttu-id="f995e-112">在 Windows 平台上，`pContext` 必须是适用于由[ICorDebugDataTarget：： GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法指定的计算机类型的 `CONTEXT` 结构（在 WinNT .h 中定义）。</span><span class="sxs-lookup"><span data-stu-id="f995e-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="f995e-113">`contextFlags` 必须具有与 `CONTEXT` 结构的 `ContextFlags` 字段相同的值。</span><span class="sxs-lookup"><span data-stu-id="f995e-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="f995e-114">`CONTEXT` 结构特定于处理器;有关详细信息，请参阅 WinNT .h 文件。</span><span class="sxs-lookup"><span data-stu-id="f995e-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f995e-115">要求</span><span class="sxs-lookup"><span data-stu-id="f995e-115">Requirements</span></span>  
 <span data-ttu-id="f995e-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f995e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f995e-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f995e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f995e-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f995e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f995e-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f995e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f995e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f995e-120">See also</span></span>

- [<span data-ttu-id="f995e-121">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="f995e-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="f995e-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="f995e-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f995e-123">调试</span><span class="sxs-lookup"><span data-stu-id="f995e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
