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
ms.openlocfilehash: a430631948230d16e5d04c869625b4c670faaf02
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868637"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="ae053-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 方法</span><span class="sxs-lookup"><span data-stu-id="ae053-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="ae053-103">获取即将运行或刚刚运行的异常子句的本机地址和帧信息（`catch`/`finally`/`filter`）。</span><span class="sxs-lookup"><span data-stu-id="ae053-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae053-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae053-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae053-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae053-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="ae053-106">弄指向描述当前异常子句实例及其关联帧的[COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ae053-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae053-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae053-107">Remarks</span></span>  
 <span data-ttu-id="ae053-108">接收到异常通知时，`GetNotifiedExceptionClauseInfo` 可用于获取要运行的异常子句（`catch`/`finally`/`filter`）的本机地址和帧信息（[ICorProfilerCallback：： ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)、 [ICorProfilerCallback：： ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)、或[ICorProfilerCallback：： ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)回调由探查器接收）或刚刚运行（[ICorProfilerCallback：： ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)、 [ICorProfilerCallback：： ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)或[ICorProfilerCallback：： ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)回调由探查器接收）。</span><span class="sxs-lookup"><span data-stu-id="ae053-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="ae053-109">此调用可以在上述任一输入回调之后的任何时候进行，直至接收到匹配的离开回调或当前子句引发了嵌套异常，在这种情况下，不会为该子句提供任何离开通知。</span><span class="sxs-lookup"><span data-stu-id="ae053-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="ae053-110">请注意，引发的异常不可能对 `filter` exception 子句进行转义，因此在这种情况下始终存在一个退出通知。</span><span class="sxs-lookup"><span data-stu-id="ae053-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae053-111">需求</span><span class="sxs-lookup"><span data-stu-id="ae053-111">Requirements</span></span>  
 <span data-ttu-id="ae053-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae053-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae053-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae053-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae053-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae053-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae053-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae053-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae053-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae053-116">See also</span></span>

- [<span data-ttu-id="ae053-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="ae053-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ae053-118">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="ae053-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
