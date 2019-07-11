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
ms.openlocfilehash: 208552dd94f587b9326280ad455ca2478ae4ac4d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780247"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="89c7b-102">ICorProfilerInfo::ForceGC 方法</span><span class="sxs-lookup"><span data-stu-id="89c7b-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="89c7b-103">强制执行在公共语言运行时 (CLR) 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="89c7b-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="89c7b-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="89c7b-105">备注</span><span class="sxs-lookup"><span data-stu-id="89c7b-105">Remarks</span></span>  
 <span data-ttu-id="89c7b-106">`ForceGC`必须仅从从未运行过托管的代码和其堆栈上没有任何探查器回调的线程调用方法。</span><span class="sxs-lookup"><span data-stu-id="89c7b-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="89c7b-107">最方便的实现是创建一个单独的线程调用的探查器内部`ForceGC`时发出信号。</span><span class="sxs-lookup"><span data-stu-id="89c7b-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89c7b-108">要求</span><span class="sxs-lookup"><span data-stu-id="89c7b-108">Requirements</span></span>  
 <span data-ttu-id="89c7b-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89c7b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c7b-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89c7b-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89c7b-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89c7b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89c7b-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c7b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c7b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="89c7b-113">See also</span></span>

- [<span data-ttu-id="89c7b-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="89c7b-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
