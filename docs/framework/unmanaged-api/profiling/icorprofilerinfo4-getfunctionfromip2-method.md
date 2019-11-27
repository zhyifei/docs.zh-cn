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
ms.openlocfilehash: 5153a25ef87d9c06bb46b74945c8eb68eb041682
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443139"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="7cca9-102">ICorProfilerInfo4::GetFunctionFromIP2 方法</span><span class="sxs-lookup"><span data-stu-id="7cca9-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="7cca9-103">将托管代码指令指针映射到函数的 JIT 重新编译版本。</span><span class="sxs-lookup"><span data-stu-id="7cca9-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cca9-104">语法</span><span class="sxs-lookup"><span data-stu-id="7cca9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cca9-105">参数</span><span class="sxs-lookup"><span data-stu-id="7cca9-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="7cca9-106">中托管代码中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="7cca9-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="7cca9-107">弄函数 ID。</span><span class="sxs-lookup"><span data-stu-id="7cca9-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="7cca9-108">弄函数的 JIT 重新编译版本的标识。</span><span class="sxs-lookup"><span data-stu-id="7cca9-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cca9-109">备注</span><span class="sxs-lookup"><span data-stu-id="7cca9-109">Remarks</span></span>  
 <span data-ttu-id="7cca9-110">`GetFunctionFromIP2` 类似于 `GetFunctionFromIP`，只不过它会获取 JIT 重新编译的 ID，而不是包含指定 IP 地址的函数的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="7cca9-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cca9-111">`GetFunctionFromIP2` 可以触发垃圾回收，而 `GetFunctionFromIP` 则不会。</span><span class="sxs-lookup"><span data-stu-id="7cca9-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="7cca9-112">有关详细信息，请参阅[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)。</span><span class="sxs-lookup"><span data-stu-id="7cca9-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cca9-113">要求</span><span class="sxs-lookup"><span data-stu-id="7cca9-113">Requirements</span></span>  
 <span data-ttu-id="7cca9-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7cca9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cca9-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7cca9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7cca9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cca9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cca9-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cca9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cca9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cca9-118">See also</span></span>

- [<span data-ttu-id="7cca9-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7cca9-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
