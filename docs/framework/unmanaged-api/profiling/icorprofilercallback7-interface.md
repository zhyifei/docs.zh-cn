---
title: ICorProfilerCallback7 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81477010b22edee71098edfc1b8557db08b6038f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049695"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="2bfa2-102">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="2bfa2-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="2bfa2-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="2bfa2-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="2bfa2-104">提供回调方法的 [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) 的子类，公共语言运行时使用该方法通知探查器已更新与内存中模块关联的符号流。</span><span class="sxs-lookup"><span data-stu-id="2bfa2-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2bfa2-105">方法</span><span class="sxs-lookup"><span data-stu-id="2bfa2-105">Methods</span></span>  
  
|<span data-ttu-id="2bfa2-106">方法</span><span class="sxs-lookup"><span data-stu-id="2bfa2-106">Method</span></span>|<span data-ttu-id="2bfa2-107">描述</span><span class="sxs-lookup"><span data-stu-id="2bfa2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2bfa2-108">ModuleInMemorySymbolsUpdated 方法</span><span class="sxs-lookup"><span data-stu-id="2bfa2-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="2bfa2-109">通知探查器已更新与内存中模块关联的符号流。</span><span class="sxs-lookup"><span data-stu-id="2bfa2-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2bfa2-110">要求</span><span class="sxs-lookup"><span data-stu-id="2bfa2-110">Requirements</span></span>  
 <span data-ttu-id="2bfa2-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bfa2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bfa2-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2bfa2-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2bfa2-113">**.NET Framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bfa2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bfa2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bfa2-114">See also</span></span>

- [<span data-ttu-id="2bfa2-115">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="2bfa2-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
