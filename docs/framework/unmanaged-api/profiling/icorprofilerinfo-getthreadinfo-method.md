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
ms.openlocfilehash: 7318d7d1494b0cf4db54b92ff09775be5500bdb1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869551"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="6770e-102">ICorProfilerInfo::GetThreadInfo 方法</span><span class="sxs-lookup"><span data-stu-id="6770e-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="6770e-103">获取指定线程的当前 Win32 线程标识。</span><span class="sxs-lookup"><span data-stu-id="6770e-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6770e-104">语法</span><span class="sxs-lookup"><span data-stu-id="6770e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6770e-105">参数</span><span class="sxs-lookup"><span data-stu-id="6770e-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="6770e-106">中要获取其当前 Win32 ID 的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="6770e-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="6770e-107">弄指向指定线程的当前 Win32 线程 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="6770e-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6770e-108">需求</span><span class="sxs-lookup"><span data-stu-id="6770e-108">Requirements</span></span>  
 <span data-ttu-id="6770e-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6770e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6770e-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6770e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6770e-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6770e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6770e-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6770e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6770e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6770e-113">See also</span></span>

- [<span data-ttu-id="6770e-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="6770e-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
