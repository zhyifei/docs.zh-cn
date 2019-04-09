---
title: ICorProfilerInfo5 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b249605833e8fbd219495ab92bebc2eff6177eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094250"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="7cdad-102">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="7cdad-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="7cdad-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="7cdad-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7cdad-104">子类[ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)提供代码探查器与公共语言运行时 (CLR)，从而控制事件监视进行通信的方法。</span><span class="sxs-lookup"><span data-stu-id="7cdad-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7cdad-105">方法</span><span class="sxs-lookup"><span data-stu-id="7cdad-105">Methods</span></span>  
  
|<span data-ttu-id="7cdad-106">方法</span><span class="sxs-lookup"><span data-stu-id="7cdad-106">Method</span></span>|<span data-ttu-id="7cdad-107">描述</span><span class="sxs-lookup"><span data-stu-id="7cdad-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7cdad-108">GetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="7cdad-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="7cdad-109">获取探查器要为其接收来自 CLR 的通知的当前事件类别。</span><span class="sxs-lookup"><span data-stu-id="7cdad-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="7cdad-110">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="7cdad-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="7cdad-111">设置一个指定事件类型的值，探查器将为该类事件接收来自 CLR 的事件通知。</span><span class="sxs-lookup"><span data-stu-id="7cdad-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cdad-112">备注</span><span class="sxs-lookup"><span data-stu-id="7cdad-112">Remarks</span></span>  
 <span data-ttu-id="7cdad-113">此接口上提供的方法旨在替换[icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)并[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7cdad-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cdad-114">要求</span><span class="sxs-lookup"><span data-stu-id="7cdad-114">Requirements</span></span>  
 <span data-ttu-id="7cdad-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7cdad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cdad-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7cdad-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="7cdad-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7cdad-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7cdad-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cdad-118">See also</span></span>

- [<span data-ttu-id="7cdad-119">分析接口</span><span class="sxs-lookup"><span data-stu-id="7cdad-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
