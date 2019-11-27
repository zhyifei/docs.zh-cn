---
title: ICorProfilerCallback3::InitializeForAttach 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: 047516574595f9ffcd61360f51823da73a2f9733
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439514"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="6203d-102">ICorProfilerCallback3::InitializeForAttach 方法</span><span class="sxs-lookup"><span data-stu-id="6203d-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="6203d-103">由公共语言运行时 (CLR) 调用，从而给予分析器一个在附加操作后可将其状态初始化的机会。</span><span class="sxs-lookup"><span data-stu-id="6203d-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6203d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6203d-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6203d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6203d-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="6203d-106">[in] `ICorProfilerInfo*` 接口的接口指针。</span><span class="sxs-lookup"><span data-stu-id="6203d-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="6203d-107">中指向传递到其 `pvClientData` 参数中的[IClrProfiling：： AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="6203d-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="6203d-108">如果此参数为 NULL，则 `cbClientData` 将为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="6203d-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="6203d-109">当 CLR 从 `InitializeForAttach` 返回时将释放此内存。</span><span class="sxs-lookup"><span data-stu-id="6203d-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="6203d-110">[in] `pvClientData` 指向的数据的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6203d-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6203d-111">备注</span><span class="sxs-lookup"><span data-stu-id="6203d-111">Remarks</span></span>  
 <span data-ttu-id="6203d-112">CLR 调用 `InitializeForAttach` 以便给予分析器请求回调的机会。</span><span class="sxs-lookup"><span data-stu-id="6203d-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6203d-113">要求</span><span class="sxs-lookup"><span data-stu-id="6203d-113">Requirements</span></span>  
 <span data-ttu-id="6203d-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6203d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6203d-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6203d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6203d-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6203d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6203d-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6203d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6203d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6203d-118">See also</span></span>

- [<span data-ttu-id="6203d-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6203d-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="6203d-120">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="6203d-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="6203d-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="6203d-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="6203d-122">分析</span><span class="sxs-lookup"><span data-stu-id="6203d-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
