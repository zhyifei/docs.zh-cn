---
title: ICorProfilerInfo4::GetFunctionFromIP2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 18099e6e658391d6dae7a666cd0cebefa5859b1a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110529"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="c5934-102">ICorProfilerInfo4::GetFunctionFromIP2 方法</span><span class="sxs-lookup"><span data-stu-id="c5934-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="c5934-103">将托管的代码指令指针映射到函数的 JIT 重新编译版本。</span><span class="sxs-lookup"><span data-stu-id="c5934-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5934-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5934-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5934-105">参数</span><span class="sxs-lookup"><span data-stu-id="c5934-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="c5934-106">[in]托管代码中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="c5934-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="c5934-107">[out]函数 id。</span><span class="sxs-lookup"><span data-stu-id="c5934-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="c5934-108">[out]该函数的 JIT 重新编译版本的标识。</span><span class="sxs-lookup"><span data-stu-id="c5934-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5934-109">备注</span><span class="sxs-lookup"><span data-stu-id="c5934-109">Remarks</span></span>  
 `GetFunctionFromIP2` <span data-ttu-id="c5934-110">类似于`GetFunctionFromIP`，只不过它所获取的 JIT 重新编译而不是包含指定的 IP 地址的函数的函数 ID ID。</span><span class="sxs-lookup"><span data-stu-id="c5934-110">is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  `GetFunctionFromIP2` <span data-ttu-id="c5934-111">可以触发垃圾收集，而`GetFunctionFromIP`将不会。</span><span class="sxs-lookup"><span data-stu-id="c5934-111">can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="c5934-112">有关详细信息，请参阅[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)。</span><span class="sxs-lookup"><span data-stu-id="c5934-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5934-113">要求</span><span class="sxs-lookup"><span data-stu-id="c5934-113">Requirements</span></span>  
 <span data-ttu-id="c5934-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5934-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5934-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5934-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5934-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5934-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c5934-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c5934-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5934-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5934-118">See also</span></span>

- [<span data-ttu-id="c5934-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c5934-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
