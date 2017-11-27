---
title: "ICorProfilerInfo::ForceGC 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.ForceGC
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3a3389c6675e992c362e3e0a77dfbc97e142ef8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="bcd89-102">ICorProfilerInfo::ForceGC 方法</span><span class="sxs-lookup"><span data-stu-id="bcd89-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="bcd89-103">强制进行垃圾回收在公共语言运行时 (CLR) 内执行。</span><span class="sxs-lookup"><span data-stu-id="bcd89-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd89-104">语法</span><span class="sxs-lookup"><span data-stu-id="bcd89-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bcd89-105">备注</span><span class="sxs-lookup"><span data-stu-id="bcd89-105">Remarks</span></span>  
 <span data-ttu-id="bcd89-106">`ForceGC`必须只从线程的从未运行托管的代码和其堆栈上没有任何探查器回调调用方法。</span><span class="sxs-lookup"><span data-stu-id="bcd89-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="bcd89-107">最方便的实现是创建一个单独的线程调用的探查器内部`ForceGC`时发出信号。</span><span class="sxs-lookup"><span data-stu-id="bcd89-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcd89-108">要求</span><span class="sxs-lookup"><span data-stu-id="bcd89-108">Requirements</span></span>  
 <span data-ttu-id="bcd89-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bcd89-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd89-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bcd89-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bcd89-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcd89-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcd89-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd89-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd89-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcd89-113">See Also</span></span>  
 [<span data-ttu-id="bcd89-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="bcd89-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
