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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b90c78d1d0b515c725cb2ebba8ad77630234b225
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468671"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="5993a-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 方法</span><span class="sxs-lookup"><span data-stu-id="5993a-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="5993a-103">获取异常子句的本机地址和帧信息 (`catch`/`finally`/`filter`)，要在运行或刚运行过。</span><span class="sxs-lookup"><span data-stu-id="5993a-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5993a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5993a-104">Syntax</span></span>  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5993a-105">参数</span><span class="sxs-lookup"><span data-stu-id="5993a-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="5993a-106">[out]一个指向[COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)结构描述当前异常子句实例及其关联的帧。</span><span class="sxs-lookup"><span data-stu-id="5993a-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5993a-107">备注</span><span class="sxs-lookup"><span data-stu-id="5993a-107">Remarks</span></span>  
 <span data-ttu-id="5993a-108">收到的异常通知后，`GetNotifiedExceptionClauseInfo`可用于获取在异常子句的本机地址和帧信息 (`catch`/`finally`/`filter`) 这是要运行 ([Icorprofilercallback:: Exceptioncatcherenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)， [icorprofilercallback:: Exceptionunwindfinallyenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)，或[icorprofilercallback:: Exceptionsearchfilterenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)回调接收由探查器) 或刚运行过 ([icorprofilercallback:: Exceptioncatcherleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)， [icorprofilercallback:: Exceptionunwindfinallyleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)，或[Icorprofilercallback:: Exceptionsearchfilterleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)回调接收由探查器)。</span><span class="sxs-lookup"><span data-stu-id="5993a-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="5993a-109">此调用可在任何时间后一个以上的 Enter 回调直到接收到匹配的保留回调或嵌套的异常引发在当前子句中，在这种情况下是该子句没有保留通知。</span><span class="sxs-lookup"><span data-stu-id="5993a-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="5993a-110">请注意，不可能引发的异常进行转义`filter`异常子句，因此始终将通知这种情况下。</span><span class="sxs-lookup"><span data-stu-id="5993a-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5993a-111">要求</span><span class="sxs-lookup"><span data-stu-id="5993a-111">Requirements</span></span>  
 <span data-ttu-id="5993a-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5993a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5993a-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5993a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5993a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5993a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5993a-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5993a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5993a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5993a-116">See also</span></span>
- [<span data-ttu-id="5993a-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5993a-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="5993a-118">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="5993a-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
