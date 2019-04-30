---
title: ICorProfilerInfo::GetCurrentThreadID 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 802072f3a0151aabc5ca5796df57ea7c694a2070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041205"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="20797-102">ICorProfilerInfo::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="20797-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="20797-103">如果它是一个托管的线程，请获取当前线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="20797-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20797-104">语法</span><span class="sxs-lookup"><span data-stu-id="20797-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20797-105">参数</span><span class="sxs-lookup"><span data-stu-id="20797-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="20797-106">[out]指向返回的托管线程 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="20797-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20797-107">备注</span><span class="sxs-lookup"><span data-stu-id="20797-107">Remarks</span></span>  
 <span data-ttu-id="20797-108">如果当前线程是一个内部运行时线程或其他非托管的线程`GetCurrentThreadID`HRESULT，并返回的值的形式返回 CORPROF_E_NOT_MANAGED_THREAD`pThreadId`参数为 null。</span><span class="sxs-lookup"><span data-stu-id="20797-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20797-109">要求</span><span class="sxs-lookup"><span data-stu-id="20797-109">Requirements</span></span>  
 <span data-ttu-id="20797-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20797-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20797-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20797-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20797-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20797-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20797-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20797-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20797-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="20797-114">See also</span></span>

- [<span data-ttu-id="20797-115">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="20797-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
