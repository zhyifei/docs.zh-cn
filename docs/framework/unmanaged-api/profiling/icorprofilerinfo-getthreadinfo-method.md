---
title: ICorProfilerInfo::GetThreadInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 405d5ff49ba7bc2e5204f00cf50c30822354e56d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775584"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="3c080-102">ICorProfilerInfo::GetThreadInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3c080-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="3c080-103">获取指定线程当前的 Win32 线程标识。</span><span class="sxs-lookup"><span data-stu-id="3c080-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c080-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c080-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c080-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c080-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="3c080-106">[in]要为其获取当前的 Win32 id。 线程的 ID</span><span class="sxs-lookup"><span data-stu-id="3c080-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="3c080-107">[out]指向指定的线程的当前 Win32 线程的 id。</span><span class="sxs-lookup"><span data-stu-id="3c080-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c080-108">要求</span><span class="sxs-lookup"><span data-stu-id="3c080-108">Requirements</span></span>  
 <span data-ttu-id="3c080-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c080-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c080-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c080-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c080-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c080-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c080-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c080-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c080-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c080-113">See also</span></span>

- [<span data-ttu-id="3c080-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="3c080-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
