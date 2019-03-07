---
title: ICorProfilerInfo::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b13402b6bccd825629b0110c948ed920c1fdf8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487962"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="6ed5e-102">ICorProfilerInfo::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="6ed5e-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="6ed5e-103">获取当前与指定的线程相关联的上下文标识。</span><span class="sxs-lookup"><span data-stu-id="6ed5e-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ed5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ed5e-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ed5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ed5e-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="6ed5e-106">[in]线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="6ed5e-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="6ed5e-107">[out]指向当前与指定的线程相关联的上下文 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="6ed5e-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="6ed5e-108">如果线程有没有当前与它关联的上下文，此函数将返回 CORPROF_E_DATAINCOMPLETE。</span><span class="sxs-lookup"><span data-stu-id="6ed5e-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ed5e-109">要求</span><span class="sxs-lookup"><span data-stu-id="6ed5e-109">Requirements</span></span>  
 <span data-ttu-id="6ed5e-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ed5e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ed5e-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ed5e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ed5e-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ed5e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ed5e-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ed5e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed5e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ed5e-114">See also</span></span>
- [<span data-ttu-id="6ed5e-115">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="6ed5e-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
