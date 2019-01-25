---
title: ICorProfilerInfo::GetHandleFromThread 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f1eb2354536a436bd6ae41cf70bf11549982d5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612588"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="8f067-102">ICorProfilerInfo::GetHandleFromThread 方法</span><span class="sxs-lookup"><span data-stu-id="8f067-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="8f067-103">映射到 Win32 线程句柄的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="8f067-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f067-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f067-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f067-105">参数</span><span class="sxs-lookup"><span data-stu-id="8f067-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="8f067-106">[in]要映射的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="8f067-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="8f067-107">[out]指向 Win32 线程句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="8f067-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f067-108">备注</span><span class="sxs-lookup"><span data-stu-id="8f067-108">Remarks</span></span>  
 <span data-ttu-id="8f067-109">探查器必须调用 Win32`DuplicateHandle`才能使用该句柄上的函数。</span><span class="sxs-lookup"><span data-stu-id="8f067-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f067-110">要求</span><span class="sxs-lookup"><span data-stu-id="8f067-110">Requirements</span></span>  
 <span data-ttu-id="8f067-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f067-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f067-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f067-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f067-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f067-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f067-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f067-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f067-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f067-115">See also</span></span>
- [<span data-ttu-id="8f067-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="8f067-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
