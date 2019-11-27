---
title: ICorProfilerCallback::JITFunctionPitched 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 9bb3934be4a2f4de4a3a235a00522c801331e1eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448426"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="500d6-102">ICorProfilerCallback::JITFunctionPitched 方法</span><span class="sxs-lookup"><span data-stu-id="500d6-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="500d6-103">通知探查器已从内存中删除了实时（JIT）编译的函数。</span><span class="sxs-lookup"><span data-stu-id="500d6-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="500d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="500d6-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="500d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="500d6-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="500d6-106">中已移除的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="500d6-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="500d6-107">备注</span><span class="sxs-lookup"><span data-stu-id="500d6-107">Remarks</span></span>  
 <span data-ttu-id="500d6-108">如果调用删除的函数，则在重新编译该函数时，探查器将接收新的 JIT 编译事件。</span><span class="sxs-lookup"><span data-stu-id="500d6-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="500d6-109">当前，公共语言运行时（CLR） JIT 编译器不会从内存中删除函数，因此，当前未使用此回调，探查器将不会接收该回调。</span><span class="sxs-lookup"><span data-stu-id="500d6-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="500d6-110">重新编译该函数之前，`functionId` 的值无效。</span><span class="sxs-lookup"><span data-stu-id="500d6-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="500d6-111">重新编译函数时，将使用相同的 `functionId` 值。</span><span class="sxs-lookup"><span data-stu-id="500d6-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="500d6-112">要求</span><span class="sxs-lookup"><span data-stu-id="500d6-112">Requirements</span></span>  
 <span data-ttu-id="500d6-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="500d6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="500d6-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="500d6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="500d6-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="500d6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="500d6-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="500d6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="500d6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="500d6-117">See also</span></span>

- [<span data-ttu-id="500d6-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="500d6-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
