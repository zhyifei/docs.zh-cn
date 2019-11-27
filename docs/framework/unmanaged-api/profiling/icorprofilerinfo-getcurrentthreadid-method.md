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
ms.openlocfilehash: fc5356f097f869403212cd234a508f1f29c5ec94
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450384"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="4e0ec-102">ICorProfilerInfo::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="4e0ec-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="4e0ec-103">获取当前线程的 ID （如果它是托管线程）。</span><span class="sxs-lookup"><span data-stu-id="4e0ec-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e0ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e0ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e0ec-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e0ec-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="4e0ec-106">弄指向托管线程的返回 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="4e0ec-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e0ec-107">备注</span><span class="sxs-lookup"><span data-stu-id="4e0ec-107">Remarks</span></span>  
 <span data-ttu-id="4e0ec-108">如果当前线程是内部运行时线程或其他非托管线程，`GetCurrentThreadID` 将作为 HRESULT 返回 CORPROF_E_NOT_MANAGED_THREAD，并且 `pThreadId` 参数的返回值将为 null。</span><span class="sxs-lookup"><span data-stu-id="4e0ec-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e0ec-109">要求</span><span class="sxs-lookup"><span data-stu-id="4e0ec-109">Requirements</span></span>  
 <span data-ttu-id="4e0ec-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e0ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e0ec-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e0ec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e0ec-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e0ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e0ec-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e0ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0ec-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e0ec-114">See also</span></span>

- [<span data-ttu-id="4e0ec-115">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4e0ec-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
