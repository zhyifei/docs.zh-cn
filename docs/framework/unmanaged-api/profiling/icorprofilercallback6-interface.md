---
title: ICorProfilerCallback6 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5025f4bb6433d193ecf7dec1d8375104147e9e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562565"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="51134-102">ICorProfilerCallback6 接口</span><span class="sxs-lookup"><span data-stu-id="51134-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="51134-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="51134-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="51134-104">子类[ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)提供公共语言运行时用于通知加载程序集的探查器的回调方法。</span><span class="sxs-lookup"><span data-stu-id="51134-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51134-105">方法</span><span class="sxs-lookup"><span data-stu-id="51134-105">Methods</span></span>  
  
|<span data-ttu-id="51134-106">方法</span><span class="sxs-lookup"><span data-stu-id="51134-106">Method</span></span>|<span data-ttu-id="51134-107">描述</span><span class="sxs-lookup"><span data-stu-id="51134-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51134-108">GetAssemblyReferences 方法</span><span class="sxs-lookup"><span data-stu-id="51134-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="51134-109">当公共语言运行时执行程序集引用闭包审核时，通知探查器程序集正处于非常早期的加载阶段。</span><span class="sxs-lookup"><span data-stu-id="51134-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51134-110">备注</span><span class="sxs-lookup"><span data-stu-id="51134-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51134-111">要求</span><span class="sxs-lookup"><span data-stu-id="51134-111">Requirements</span></span>  
 <span data-ttu-id="51134-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51134-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51134-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51134-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51134-114">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51134-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51134-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="51134-115">See also</span></span>
- [<span data-ttu-id="51134-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="51134-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
