---
title: ICorProfilerInfo5::SetEventMask2 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22a783b7564c3545edea93bf4faca1fc40b54cec
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499792"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="6dbc5-102">ICorProfilerInfo5::SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="6dbc5-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="6dbc5-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="6dbc5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6dbc5-104">设置一个值，用于指定探查器需要从公共语言运行时 (CLR) 接收其事件通知的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="6dbc5-105">它提供了更多的功能比[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dbc5-106">语法</span><span class="sxs-lookup"><span data-stu-id="6dbc5-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dbc5-107">参数</span><span class="sxs-lookup"><span data-stu-id="6dbc5-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="6dbc5-108">[in] 一个指定事件类别的 4 字节的值。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="6dbc5-109">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="6dbc5-110">在中描述了这些位[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="6dbc5-111">[in] 一个指定事件类别的 4 字节的值。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="6dbc5-112">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="6dbc5-113">在中描述了这些位[COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dbc5-114">备注</span><span class="sxs-lookup"><span data-stu-id="6dbc5-114">Remarks</span></span>  
 <span data-ttu-id="6dbc5-115">`SetEventMask2` 方法用于设置探查器订阅的回调。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="6dbc5-116">通常情况下，调用[GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)方法，以确定设置哪些位，执行逻辑或其`pdwEventsLow`并`pdwEventsHigh`值以及你想要设置，然后调用任何新位`SetEventMask2`方法。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="6dbc5-117">此方法是为建议的替代项[SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dbc5-118">要求</span><span class="sxs-lookup"><span data-stu-id="6dbc5-118">Requirements</span></span>  
 <span data-ttu-id="6dbc5-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6dbc5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dbc5-120">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6dbc5-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6dbc5-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dbc5-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dbc5-122">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dbc5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbc5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="6dbc5-123">See also</span></span>
- [<span data-ttu-id="6dbc5-124">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="6dbc5-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="6dbc5-125">GetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="6dbc5-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
