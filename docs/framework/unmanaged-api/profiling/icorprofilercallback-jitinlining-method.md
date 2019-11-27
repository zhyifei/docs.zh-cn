---
title: ICorProfilerCallback::JITInlining 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449900"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="ff406-102">ICorProfilerCallback::JITInlining 方法</span><span class="sxs-lookup"><span data-stu-id="ff406-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="ff406-103">通知探查器，实时（JIT）编译器将与另一个函数插入一个函数。</span><span class="sxs-lookup"><span data-stu-id="ff406-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff406-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff406-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff406-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff406-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="ff406-106">中将在其中插入 `calleeId` 函数的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="ff406-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="ff406-107">中要插入的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="ff406-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="ff406-108">[out] 用于允许插入的 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="ff406-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff406-109">备注</span><span class="sxs-lookup"><span data-stu-id="ff406-109">Remarks</span></span>  
 <span data-ttu-id="ff406-110">探查器可以将 `pfShouldInline` 设置为 `false`，以防止 `calleeId` 函数插入 `callerId` 函数。</span><span class="sxs-lookup"><span data-stu-id="ff406-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="ff406-111">此外，探查器可以通过使用[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举的 COR_PRF_DISABLE_INLINING 值全局禁用内联插入。</span><span class="sxs-lookup"><span data-stu-id="ff406-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="ff406-112">以内联方式插入的函数不会引发用于进入或离开的事件。</span><span class="sxs-lookup"><span data-stu-id="ff406-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="ff406-113">因此，探查器必须将 `pfShouldInline` 设置为 `false` 才能生成准确的调用图。</span><span class="sxs-lookup"><span data-stu-id="ff406-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="ff406-114">将 `pfShouldInline` 设置为 `false` 会影响性能，因为内联插入通常会提高速度，并减少插入方法的单独 JIT 编译事件数。</span><span class="sxs-lookup"><span data-stu-id="ff406-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff406-115">要求</span><span class="sxs-lookup"><span data-stu-id="ff406-115">Requirements</span></span>  
 <span data-ttu-id="ff406-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff406-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff406-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff406-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff406-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff406-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff406-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff406-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff406-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff406-120">See also</span></span>

- [<span data-ttu-id="ff406-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ff406-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
