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
ms.openlocfilehash: a22a0de9a20f32ce1c9818bbcf29222a4b331420
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862420"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="8c86a-102">ICorProfilerInfo3::EnumJITedFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="8c86a-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="8c86a-103">返回之前 JIT 编译的所有函数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="8c86a-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c86a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c86a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c86a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8c86a-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8c86a-106">弄指向[ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="8c86a-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c86a-107">备注</span><span class="sxs-lookup"><span data-stu-id="8c86a-107">Remarks</span></span>  
 <span data-ttu-id="8c86a-108">此方法可能与 `JITCompilation` 回调（如[ICorProfilerCallback：： JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)方法）重叠。</span><span class="sxs-lookup"><span data-stu-id="8c86a-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="8c86a-109">此方法返回的枚举器不包括从使用 Ngen.exe 生成的本机映像加载的函数。</span><span class="sxs-lookup"><span data-stu-id="8c86a-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c86a-110">对于 "`COR_PRF_FUNCTION::reJitId`" 字段的值，返回的枚举只包含 "0"。</span><span class="sxs-lookup"><span data-stu-id="8c86a-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="8c86a-111">如果需要有效 `COR_PRF_FUNCTION::reJitId` 值，请使用[ICorProfilerInfo4：： EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8c86a-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c86a-112">需求</span><span class="sxs-lookup"><span data-stu-id="8c86a-112">Requirements</span></span>  
 <span data-ttu-id="8c86a-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c86a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c86a-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c86a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c86a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c86a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c86a-116">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c86a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c86a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c86a-117">See also</span></span>

- [<span data-ttu-id="8c86a-118">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="8c86a-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="8c86a-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="8c86a-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="8c86a-120">分析</span><span class="sxs-lookup"><span data-stu-id="8c86a-120">Profiling</span></span>](index.md)
