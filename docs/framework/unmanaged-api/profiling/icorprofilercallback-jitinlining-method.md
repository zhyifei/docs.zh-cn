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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92060147677fec5c772b16a61fa6ed5c294132fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471483"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="516d4-102">ICorProfilerCallback::JITInlining 方法</span><span class="sxs-lookup"><span data-stu-id="516d4-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="516d4-103">通知探查器实时 (JIT) 编译器将要插入一个嵌入另一个函数。</span><span class="sxs-lookup"><span data-stu-id="516d4-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="516d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="516d4-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="516d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="516d4-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="516d4-106">[in]在其中函数的 ID`calleeId`将插入函数。</span><span class="sxs-lookup"><span data-stu-id="516d4-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="516d4-107">[in]要插入该函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="516d4-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="516d4-108">[out]`true`若要允许插入发生; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="516d4-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="516d4-109">备注</span><span class="sxs-lookup"><span data-stu-id="516d4-109">Remarks</span></span>  
 <span data-ttu-id="516d4-110">探查器可以设置`pfShouldInline`到`false`以免`calleeId`函数中要插入到`callerId`函数。</span><span class="sxs-lookup"><span data-stu-id="516d4-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="516d4-111">此外，探查器可以全局内联插入使用禁用的 COR_PRF_DISABLE_INLINING 值[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="516d4-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="516d4-112">内联函数插入不会引发事件进入或离开。</span><span class="sxs-lookup"><span data-stu-id="516d4-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="516d4-113">因此，探查器必须设置`pfShouldInline`到`false`为了生成准确的调用关系图。</span><span class="sxs-lookup"><span data-stu-id="516d4-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="516d4-114">设置`pfShouldInline`到`false`会影响性能，因为内联插入通常会提高速度和减少了单独的插入方法的 JIT 编译事件数。</span><span class="sxs-lookup"><span data-stu-id="516d4-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="516d4-115">要求</span><span class="sxs-lookup"><span data-stu-id="516d4-115">Requirements</span></span>  
 <span data-ttu-id="516d4-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="516d4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="516d4-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="516d4-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="516d4-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="516d4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="516d4-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="516d4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="516d4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="516d4-120">See also</span></span>
- [<span data-ttu-id="516d4-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="516d4-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
