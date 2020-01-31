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
ms.openlocfilehash: 90071121411b706052e1cbb4cb647536dae2835a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864864"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="0e685-102">ICorProfilerCallback6 接口</span><span class="sxs-lookup"><span data-stu-id="0e685-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="0e685-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="0e685-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0e685-104">提供回调方法的[ICorProfilerCallback5](icorprofilercallback5-interface.md)的子类，公共语言运行时使用该方法通知探查器正在加载程序集。</span><span class="sxs-lookup"><span data-stu-id="0e685-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e685-105">方法</span><span class="sxs-lookup"><span data-stu-id="0e685-105">Methods</span></span>  
  
|<span data-ttu-id="0e685-106">方法</span><span class="sxs-lookup"><span data-stu-id="0e685-106">Method</span></span>|<span data-ttu-id="0e685-107">描述</span><span class="sxs-lookup"><span data-stu-id="0e685-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e685-108">GetAssemblyReferences 方法</span><span class="sxs-lookup"><span data-stu-id="0e685-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="0e685-109">当公共语言运行时执行程序集引用闭包审核时，通知探查器程序集正处于非常早期的加载阶段。</span><span class="sxs-lookup"><span data-stu-id="0e685-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e685-110">备注</span><span class="sxs-lookup"><span data-stu-id="0e685-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e685-111">需求</span><span class="sxs-lookup"><span data-stu-id="0e685-111">Requirements</span></span>  
 <span data-ttu-id="0e685-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e685-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e685-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e685-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e685-114">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e685-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e685-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e685-115">See also</span></span>

- [<span data-ttu-id="0e685-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="0e685-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
