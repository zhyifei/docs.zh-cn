---
title: ICorProfilerCallback2::ThreadNameChanged 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0102c2b8269d8a716a75b3f411b8e177f500eb4a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470570"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="d81b9-102">ICorProfilerCallback2::ThreadNameChanged 方法</span><span class="sxs-lookup"><span data-stu-id="d81b9-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="d81b9-103">通知代码探查器线程的名称已更改。</span><span class="sxs-lookup"><span data-stu-id="d81b9-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="d81b9-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d81b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="d81b9-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="d81b9-106">[in]线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="d81b9-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d81b9-107">[in]该线程的新名称的长度。</span><span class="sxs-lookup"><span data-stu-id="d81b9-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="d81b9-108">[in]新线程的名称。</span><span class="sxs-lookup"><span data-stu-id="d81b9-108">[in] The new name of the thread.</span></span> <span data-ttu-id="d81b9-109">名称不以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="d81b9-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d81b9-110">要求</span><span class="sxs-lookup"><span data-stu-id="d81b9-110">Requirements</span></span>  
 <span data-ttu-id="d81b9-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d81b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d81b9-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d81b9-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d81b9-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d81b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d81b9-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d81b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81b9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d81b9-115">See also</span></span>
- [<span data-ttu-id="d81b9-116">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d81b9-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d81b9-117">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="d81b9-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
