---
title: ICorProfilerInfo5::GetEventMask2 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8973e100694be0f50b575d978f3327b8b3a1d334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455659"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="2fd16-102">ICorProfilerInfo5::GetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="2fd16-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="2fd16-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="2fd16-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2fd16-104">获取探查器要从公共语言运行时 (CLR) 中接收通知的当前事件类别。</span><span class="sxs-lookup"><span data-stu-id="2fd16-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="2fd16-105">它提供了功能不是由[icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2fd16-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd16-106">语法</span><span class="sxs-lookup"><span data-stu-id="2fd16-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2fd16-107">参数</span><span class="sxs-lookup"><span data-stu-id="2fd16-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="2fd16-108">[out] 一个指向指定事件类别的 4 字节值的指针。</span><span class="sxs-lookup"><span data-stu-id="2fd16-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="2fd16-109">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="2fd16-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="2fd16-110">中描述了这些位[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="2fd16-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="2fd16-111">[out] 一个指向指定事件类别的 4 字节值的指针。</span><span class="sxs-lookup"><span data-stu-id="2fd16-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="2fd16-112">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="2fd16-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="2fd16-113">中描述了这些位[COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="2fd16-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fd16-114">备注</span><span class="sxs-lookup"><span data-stu-id="2fd16-114">Remarks</span></span>  
 <span data-ttu-id="2fd16-115">`GetEventMask2` 方法用于确定探查器已订阅了哪些回调。</span><span class="sxs-lookup"><span data-stu-id="2fd16-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="2fd16-116">通常，你可以执行的逻辑 OR`pdwEventsLow`和`pdwEventsHigh`值以及你想要设置，然后调用任何新位[SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2fd16-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="2fd16-117">此方法是建议的替代项为[GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2fd16-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd16-118">要求</span><span class="sxs-lookup"><span data-stu-id="2fd16-118">Requirements</span></span>  
 <span data-ttu-id="2fd16-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd16-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fd16-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2fd16-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2fd16-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fd16-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fd16-122">**.NET framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fd16-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd16-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fd16-123">See Also</span></span>  
 [<span data-ttu-id="2fd16-124">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="2fd16-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [<span data-ttu-id="2fd16-125">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="2fd16-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
