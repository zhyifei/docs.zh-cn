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
ms.openlocfilehash: f8eff85392d355ea54980ac6b29e3c4cebb1b240
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869590"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="ef3de-102">ICorProfilerInfo::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="ef3de-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="ef3de-103">获取当前与指定线程关联的上下文标识。</span><span class="sxs-lookup"><span data-stu-id="ef3de-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3de-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef3de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef3de-105">参数</span><span class="sxs-lookup"><span data-stu-id="ef3de-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ef3de-106">中线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="ef3de-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="ef3de-107">弄指向当前与指定线程关联的上下文 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="ef3de-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="ef3de-108">如果该线程当前没有关联的上下文，则此函数将返回 CORPROF_E_DATAINCOMPLETE。</span><span class="sxs-lookup"><span data-stu-id="ef3de-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef3de-109">需求</span><span class="sxs-lookup"><span data-stu-id="ef3de-109">Requirements</span></span>  
 <span data-ttu-id="ef3de-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3de-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef3de-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef3de-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef3de-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef3de-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef3de-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef3de-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3de-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef3de-114">See also</span></span>

- [<span data-ttu-id="ef3de-115">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="ef3de-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
