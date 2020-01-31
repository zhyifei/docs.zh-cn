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
ms.openlocfilehash: d0219751987b1f2d78ee37a1553b323014c1ccfe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865683"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="913e1-102">ICorProfilerCallback3::InitializeForAttach 方法</span><span class="sxs-lookup"><span data-stu-id="913e1-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="913e1-103">由公共语言运行时 (CLR) 调用，从而给予分析器一个在附加操作后可将其状态初始化的机会。</span><span class="sxs-lookup"><span data-stu-id="913e1-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="913e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="913e1-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="913e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="913e1-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="913e1-106">[in] `ICorProfilerInfo*` 接口的接口指针。</span><span class="sxs-lookup"><span data-stu-id="913e1-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="913e1-107">中指向传递到其 `pvClientData` 参数中的[IClrProfiling：： AttachProfiler](iclrprofiling-attachprofiler-method.md)方法的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="913e1-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="913e1-108">如果此参数为 NULL，则 `cbClientData` 将为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="913e1-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="913e1-109">当 CLR 从 `InitializeForAttach` 返回时将释放此内存。</span><span class="sxs-lookup"><span data-stu-id="913e1-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="913e1-110">[in] `pvClientData` 指向的数据的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="913e1-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="913e1-111">备注</span><span class="sxs-lookup"><span data-stu-id="913e1-111">Remarks</span></span>  
 <span data-ttu-id="913e1-112">CLR 调用 `InitializeForAttach` 以便给予分析器请求回调的机会。</span><span class="sxs-lookup"><span data-stu-id="913e1-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="913e1-113">需求</span><span class="sxs-lookup"><span data-stu-id="913e1-113">Requirements</span></span>  
 <span data-ttu-id="913e1-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="913e1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="913e1-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="913e1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="913e1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="913e1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="913e1-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="913e1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913e1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="913e1-118">See also</span></span>

- [<span data-ttu-id="913e1-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="913e1-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="913e1-120">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="913e1-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="913e1-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="913e1-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="913e1-122">分析</span><span class="sxs-lookup"><span data-stu-id="913e1-122">Profiling</span></span>](index.md)
