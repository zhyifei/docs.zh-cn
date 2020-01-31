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
ms.openlocfilehash: 10e84b729c8af607165009a8591a69dbc1afcb1e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868377"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="a7e19-102">ICorProfilerInfo5::SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="a7e19-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="a7e19-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="a7e19-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a7e19-104">设置一个值，用于指定探查器需要从公共语言运行时 (CLR) 接收其事件通知的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="a7e19-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="a7e19-105">它提供的功能比[ICorProfilerInfo：： SetEventMask](icorprofilerinfo-seteventmask-method.md)方法更多。</span><span class="sxs-lookup"><span data-stu-id="a7e19-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e19-106">语法</span><span class="sxs-lookup"><span data-stu-id="a7e19-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7e19-107">参数</span><span class="sxs-lookup"><span data-stu-id="a7e19-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="a7e19-108">[in] 一个指定事件类别的 4 字节的值。</span><span class="sxs-lookup"><span data-stu-id="a7e19-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="a7e19-109">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="a7e19-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="a7e19-110">[COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)枚举中描述了这些位。</span><span class="sxs-lookup"><span data-stu-id="a7e19-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="a7e19-111">[in] 一个指定事件类别的 4 字节的值。</span><span class="sxs-lookup"><span data-stu-id="a7e19-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="a7e19-112">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="a7e19-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="a7e19-113">[COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)枚举中描述了这些位。</span><span class="sxs-lookup"><span data-stu-id="a7e19-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7e19-114">备注</span><span class="sxs-lookup"><span data-stu-id="a7e19-114">Remarks</span></span>  
 <span data-ttu-id="a7e19-115">`SetEventMask2` 方法用于设置探查器订阅的回调。</span><span class="sxs-lookup"><span data-stu-id="a7e19-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="a7e19-116">通常，你可以调用[GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)方法来确定设置了哪些位、执行 `pdwEventsLow` 的逻辑或，并 `pdwEventsHigh` 值和要设置的任何新位，然后调用 `SetEventMask2` 方法。</span><span class="sxs-lookup"><span data-stu-id="a7e19-116">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="a7e19-117">此方法是[SetEventMask](icorprofilerinfo-seteventmask-method.md)方法的建议替代方法。</span><span class="sxs-lookup"><span data-stu-id="a7e19-117">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7e19-118">需求</span><span class="sxs-lookup"><span data-stu-id="a7e19-118">Requirements</span></span>  
 <span data-ttu-id="a7e19-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e19-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e19-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7e19-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7e19-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7e19-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7e19-122">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e19-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e19-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7e19-123">See also</span></span>

- [<span data-ttu-id="a7e19-124">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="a7e19-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="a7e19-125">GetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="a7e19-125">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
