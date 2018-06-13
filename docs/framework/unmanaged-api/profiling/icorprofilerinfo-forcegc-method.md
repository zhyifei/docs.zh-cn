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
ms.openlocfilehash: 06601b1aa675dd9ecf023a9f83d881ba1591ac52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454468"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="1faac-102">ICorProfilerInfo::ForceGC 方法</span><span class="sxs-lookup"><span data-stu-id="1faac-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="1faac-103">强制进行垃圾回收在公共语言运行时 (CLR) 内执行。</span><span class="sxs-lookup"><span data-stu-id="1faac-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1faac-104">语法</span><span class="sxs-lookup"><span data-stu-id="1faac-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1faac-105">备注</span><span class="sxs-lookup"><span data-stu-id="1faac-105">Remarks</span></span>  
 <span data-ttu-id="1faac-106">`ForceGC`必须只从线程的从未运行托管的代码和其堆栈上没有任何探查器回调调用方法。</span><span class="sxs-lookup"><span data-stu-id="1faac-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="1faac-107">最方便的实现是创建一个单独的线程调用的探查器内部`ForceGC`时发出信号。</span><span class="sxs-lookup"><span data-stu-id="1faac-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1faac-108">要求</span><span class="sxs-lookup"><span data-stu-id="1faac-108">Requirements</span></span>  
 <span data-ttu-id="1faac-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1faac-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1faac-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1faac-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1faac-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1faac-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1faac-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1faac-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1faac-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1faac-113">See Also</span></span>  
 [<span data-ttu-id="1faac-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1faac-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
