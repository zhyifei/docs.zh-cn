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
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863941"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="9c822-102">ICorProfilerInfo::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="9c822-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="9c822-103">获取当前线程的 ID （如果它是托管线程）。</span><span class="sxs-lookup"><span data-stu-id="9c822-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c822-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c822-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c822-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c822-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="9c822-106">弄指向托管线程的返回 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="9c822-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c822-107">备注</span><span class="sxs-lookup"><span data-stu-id="9c822-107">Remarks</span></span>  
 <span data-ttu-id="9c822-108">如果当前线程是内部运行时线程或其他非托管线程，`GetCurrentThreadID` 将作为 HRESULT 返回 CORPROF_E_NOT_MANAGED_THREAD，并且 `pThreadId` 参数的返回值将为 null。</span><span class="sxs-lookup"><span data-stu-id="9c822-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c822-109">需求</span><span class="sxs-lookup"><span data-stu-id="9c822-109">Requirements</span></span>  
 <span data-ttu-id="9c822-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c822-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c822-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c822-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c822-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c822-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c822-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c822-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c822-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c822-114">See also</span></span>

- [<span data-ttu-id="9c822-115">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="9c822-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
