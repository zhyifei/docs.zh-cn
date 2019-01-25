---
title: ICorProfilerInfo3::EnumJITedFunctions 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12f5930fb6d4e149653bc29d2f36b0df72c71447
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498825"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="ac86c-102">ICorProfilerInfo3::EnumJITedFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="ac86c-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="ac86c-103">返回先前 JIT 编译的所有功能的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ac86c-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac86c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac86c-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac86c-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac86c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="ac86c-106">[out]一个指向[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)枚举器。</span><span class="sxs-lookup"><span data-stu-id="ac86c-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac86c-107">备注</span><span class="sxs-lookup"><span data-stu-id="ac86c-107">Remarks</span></span>  
 <span data-ttu-id="ac86c-108">此方法可能会与重叠`JITCompilation`如回调[icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ac86c-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="ac86c-109">此方法返回的枚举器不包括从使用 Ngen.exe 生成本机映像加载的函数。</span><span class="sxs-lookup"><span data-stu-id="ac86c-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac86c-110">返回的枚举包括仅"0"的值的`COR_PRF_FUNCTION::reJitId`字段。</span><span class="sxs-lookup"><span data-stu-id="ac86c-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="ac86c-111">如果您需要有效`COR_PRF_FUNCTION::reJitId`值，请使用[ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ac86c-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac86c-112">要求</span><span class="sxs-lookup"><span data-stu-id="ac86c-112">Requirements</span></span>  
 <span data-ttu-id="ac86c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac86c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac86c-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac86c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac86c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac86c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac86c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac86c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac86c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac86c-117">See also</span></span>
- [<span data-ttu-id="ac86c-118">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="ac86c-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ac86c-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="ac86c-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ac86c-120">分析</span><span class="sxs-lookup"><span data-stu-id="ac86c-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
