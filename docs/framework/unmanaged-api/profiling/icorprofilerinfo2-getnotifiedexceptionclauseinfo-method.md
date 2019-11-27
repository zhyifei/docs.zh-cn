---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: 52ad124638a1c1ec7d39fa41b9163f3ab50ffe70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433069"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="285c6-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 方法</span><span class="sxs-lookup"><span data-stu-id="285c6-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="285c6-103">获取即将运行或刚刚运行的异常子句的本机地址和帧信息（`catch`/`finally`/`filter`）。</span><span class="sxs-lookup"><span data-stu-id="285c6-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="285c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="285c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="285c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="285c6-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="285c6-106">弄指向描述当前异常子句实例及其关联帧的[COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="285c6-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="285c6-107">备注</span><span class="sxs-lookup"><span data-stu-id="285c6-107">Remarks</span></span>  
 <span data-ttu-id="285c6-108">接收到异常通知时，`GetNotifiedExceptionClauseInfo` 可用于获取要运行的异常子句（`catch`/`finally`/`filter`）的本机地址和帧信息（[ICorProfilerCallback：： ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)、 [ICorProfilerCallback：： ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)、或[ICorProfilerCallback：： ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)回调由探查器接收）或刚刚运行（[ICorProfilerCallback：： ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)、 [ICorProfilerCallback：： ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)或[ICorProfilerCallback：： ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)回调由探查器接收）。</span><span class="sxs-lookup"><span data-stu-id="285c6-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="285c6-109">此调用可以在上述任一输入回调之后的任何时候进行，直至接收到匹配的离开回调或当前子句引发了嵌套异常，在这种情况下，不会为该子句提供任何离开通知。</span><span class="sxs-lookup"><span data-stu-id="285c6-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="285c6-110">请注意，引发的异常不可能对 `filter` exception 子句进行转义，因此在这种情况下始终存在一个退出通知。</span><span class="sxs-lookup"><span data-stu-id="285c6-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="285c6-111">要求</span><span class="sxs-lookup"><span data-stu-id="285c6-111">Requirements</span></span>  
 <span data-ttu-id="285c6-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="285c6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="285c6-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="285c6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="285c6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="285c6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="285c6-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="285c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="285c6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="285c6-116">See also</span></span>

- [<span data-ttu-id="285c6-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="285c6-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="285c6-118">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="285c6-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
