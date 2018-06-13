---
title: ICorProfilerInfo::SetEventMask 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3834efbf9725e0ceed670fd3494c784f49968810
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455207"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="c4c10-102">ICorProfilerInfo::SetEventMask 方法</span><span class="sxs-lookup"><span data-stu-id="c4c10-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="c4c10-103">设置一个值，用于指定探查器需要从公共语言运行时 (CLR) 接收其相关通知的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="c4c10-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c10-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4c10-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4c10-105">参数</span><span class="sxs-lookup"><span data-stu-id="c4c10-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="c4c10-106">[in] 一个指定事件类别的 4 字节的值。</span><span class="sxs-lookup"><span data-stu-id="c4c10-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="c4c10-107">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="c4c10-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="c4c10-108">中描述了这些位[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="c4c10-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4c10-109">备注</span><span class="sxs-lookup"><span data-stu-id="c4c10-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4c10-110">应调用[SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法而非此方法。</span><span class="sxs-lookup"><span data-stu-id="c4c10-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="c4c10-111">尽管`SetEventMask`方法继续支持， [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)提供其他功能。</span><span class="sxs-lookup"><span data-stu-id="c4c10-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4c10-112">要求</span><span class="sxs-lookup"><span data-stu-id="c4c10-112">Requirements</span></span>  
 <span data-ttu-id="c4c10-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c10-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4c10-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4c10-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4c10-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4c10-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4c10-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4c10-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c10-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4c10-117">See Also</span></span>  
 [<span data-ttu-id="c4c10-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c4c10-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="c4c10-119">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="c4c10-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
