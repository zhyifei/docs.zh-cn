---
title: ICorProfilerInfo::ForceGC 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5672d1b89b4260d1ebfbf444deb2702f215a0e95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078078"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="42378-102">ICorProfilerInfo::ForceGC 方法</span><span class="sxs-lookup"><span data-stu-id="42378-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="42378-103">强制执行在公共语言运行时 (CLR) 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="42378-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42378-104">语法</span><span class="sxs-lookup"><span data-stu-id="42378-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="42378-105">备注</span><span class="sxs-lookup"><span data-stu-id="42378-105">Remarks</span></span>  
 <span data-ttu-id="42378-106">`ForceGC`必须仅从从未运行过托管的代码和其堆栈上没有任何探查器回调的线程调用方法。</span><span class="sxs-lookup"><span data-stu-id="42378-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="42378-107">最方便的实现是创建一个单独的线程调用的探查器内部`ForceGC`时发出信号。</span><span class="sxs-lookup"><span data-stu-id="42378-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42378-108">要求</span><span class="sxs-lookup"><span data-stu-id="42378-108">Requirements</span></span>  
 <span data-ttu-id="42378-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42378-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42378-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42378-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42378-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42378-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42378-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42378-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42378-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="42378-113">See also</span></span>

- [<span data-ttu-id="42378-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="42378-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
