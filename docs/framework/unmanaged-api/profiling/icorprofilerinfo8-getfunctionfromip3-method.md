---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 6d50a5d74eccff6fe39aca111f768bac4d8f2e2e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868325"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="a2388-102">ICorProfilerInfo8：： GetFunctionFromIP3 方法</span><span class="sxs-lookup"><span data-stu-id="a2388-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="a2388-103">将托管代码指令指针映射到 FunctionID。</span><span class="sxs-lookup"><span data-stu-id="a2388-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="a2388-104">此方法适用于动态和非动态方法。</span><span class="sxs-lookup"><span data-stu-id="a2388-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2388-105">语法</span><span class="sxs-lookup"><span data-stu-id="a2388-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="a2388-106">参数</span><span class="sxs-lookup"><span data-stu-id="a2388-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="a2388-107">\[中的] 托管代码中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="a2388-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="a2388-108">\[out] 函数 ID。</span><span class="sxs-lookup"><span data-stu-id="a2388-108">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="a2388-109">\[out] 函数的 JIT 重新编译版本的标识。</span><span class="sxs-lookup"><span data-stu-id="a2388-109">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2388-110">备注</span><span class="sxs-lookup"><span data-stu-id="a2388-110">Remarks</span></span>

<span data-ttu-id="a2388-111">此方法适用于动态和非动态方法。</span><span class="sxs-lookup"><span data-stu-id="a2388-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="a2388-112">它是[GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)的超集，只适用于具有元数据的函数。</span><span class="sxs-lookup"><span data-stu-id="a2388-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2388-113">需求</span><span class="sxs-lookup"><span data-stu-id="a2388-113">Requirements</span></span>

<span data-ttu-id="a2388-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2388-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a2388-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2388-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a2388-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2388-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a2388-117">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a2388-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a2388-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2388-118">See also</span></span>

- [<span data-ttu-id="a2388-119">ICorProfilerInfo8 接口</span><span class="sxs-lookup"><span data-stu-id="a2388-119">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
