---
title: "ICorProfilerInfo5 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 75bbaf5fdf41a55719965203c50ddd0f5d48263a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="4c50c-102">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="4c50c-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="4c50c-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="4c50c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4c50c-104">一个子类[ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)提供代码探查器用于与公共语言运行时 (CLR)，从而控制事件监视通信的方法。</span><span class="sxs-lookup"><span data-stu-id="4c50c-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c50c-105">方法</span><span class="sxs-lookup"><span data-stu-id="4c50c-105">Methods</span></span>  
  
|<span data-ttu-id="4c50c-106">方法</span><span class="sxs-lookup"><span data-stu-id="4c50c-106">Method</span></span>|<span data-ttu-id="4c50c-107">描述</span><span class="sxs-lookup"><span data-stu-id="4c50c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c50c-108">GetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="4c50c-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="4c50c-109">获取探查器要为其接收来自 CLR 的通知的当前事件类别。</span><span class="sxs-lookup"><span data-stu-id="4c50c-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="4c50c-110">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="4c50c-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="4c50c-111">设置一个指定事件类型的值，探查器将为该类事件接收来自 CLR 的事件通知。</span><span class="sxs-lookup"><span data-stu-id="4c50c-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c50c-112">备注</span><span class="sxs-lookup"><span data-stu-id="4c50c-112">Remarks</span></span>  
 <span data-ttu-id="4c50c-113">此接口上提供的方法旨在替换[icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)和[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4c50c-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c50c-114">惠?</span><span class="sxs-lookup"><span data-stu-id="4c50c-114">Requirements</span></span>  
 <span data-ttu-id="4c50c-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c50c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c50c-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4c50c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c50c-117">**.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c50c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c50c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c50c-118">See Also</span></span>  
 [<span data-ttu-id="4c50c-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="4c50c-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
