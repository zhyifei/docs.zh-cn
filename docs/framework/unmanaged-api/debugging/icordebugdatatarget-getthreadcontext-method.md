---
title: "ICorDebugDataTarget::GetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetThreadContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 543956bb42d7477456426d7327f14b059b23d759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="14546-102">ICorDebugDataTarget::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="14546-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="14546-103">返回指定的线程的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="14546-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14546-104">语法</span><span class="sxs-lookup"><span data-stu-id="14546-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14546-105">参数</span><span class="sxs-lookup"><span data-stu-id="14546-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="14546-106">[in]要检索其上下文的线程标识符。</span><span class="sxs-lookup"><span data-stu-id="14546-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="14546-107">由操作系统定义的标识符。</span><span class="sxs-lookup"><span data-stu-id="14546-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="14546-108">[in]应读取依赖于平台的标志，指示上下文的哪些部分的按位组合。</span><span class="sxs-lookup"><span data-stu-id="14546-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="14546-109">[输入] `pContext` 的大小。</span><span class="sxs-lookup"><span data-stu-id="14546-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="14546-110">[out]将存储的线程上下文缓冲区。</span><span class="sxs-lookup"><span data-stu-id="14546-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14546-111">备注</span><span class="sxs-lookup"><span data-stu-id="14546-111">Remarks</span></span>  
 <span data-ttu-id="14546-112">在 Windows 平台上`pContext`必须`CONTEXT`（在 WinNT.h 中定义） 的结构，它是适用于由指定的计算机类型[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="14546-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="14546-113">`contextFlags`必须具有相同的值`ContextFlags`字段`CONTEXT`结构。</span><span class="sxs-lookup"><span data-stu-id="14546-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="14546-114">`CONTEXT`结构是特定于处理器的; WinNT.h 中的文件，了解详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="14546-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14546-115">要求</span><span class="sxs-lookup"><span data-stu-id="14546-115">Requirements</span></span>  
 <span data-ttu-id="14546-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14546-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14546-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14546-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14546-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14546-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14546-119">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14546-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14546-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14546-120">See Also</span></span>  
 [<span data-ttu-id="14546-121">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="14546-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="14546-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="14546-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="14546-123">调试</span><span class="sxs-lookup"><span data-stu-id="14546-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
