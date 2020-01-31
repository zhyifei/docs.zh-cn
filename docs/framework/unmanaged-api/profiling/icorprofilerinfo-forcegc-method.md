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
ms.openlocfilehash: e1fe38419cda328c919f0840d51cf6336919aa60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864188"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="d65d5-102">ICorProfilerInfo::ForceGC 方法</span><span class="sxs-lookup"><span data-stu-id="d65d5-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="d65d5-103">强制在公共语言运行时（CLR）内发生垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d65d5-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d65d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="d65d5-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d65d5-105">备注</span><span class="sxs-lookup"><span data-stu-id="d65d5-105">Remarks</span></span>  
 <span data-ttu-id="d65d5-106">只能从从未运行托管代码且在其堆栈上没有任何探查器回调的线程调用 `ForceGC` 方法。</span><span class="sxs-lookup"><span data-stu-id="d65d5-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="d65d5-107">最方便的实现是在探查器中创建一个单独的线程，该线程在发出信号时调用 `ForceGC`。</span><span class="sxs-lookup"><span data-stu-id="d65d5-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d65d5-108">需求</span><span class="sxs-lookup"><span data-stu-id="d65d5-108">Requirements</span></span>  
 <span data-ttu-id="d65d5-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d65d5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d65d5-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d65d5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d65d5-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d65d5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d65d5-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d65d5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65d5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d65d5-113">See also</span></span>

- [<span data-ttu-id="d65d5-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="d65d5-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
