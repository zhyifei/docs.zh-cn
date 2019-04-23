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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84d07fe975bab1b0af81299893b52142630b5bb9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079742"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="33f66-102">ICorProfilerCallback3::InitializeForAttach 方法</span><span class="sxs-lookup"><span data-stu-id="33f66-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="33f66-103">由公共语言运行时 (CLR) 调用，从而给予分析器一个在附加操作后可将其状态初始化的机会。</span><span class="sxs-lookup"><span data-stu-id="33f66-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f66-104">语法</span><span class="sxs-lookup"><span data-stu-id="33f66-104">Syntax</span></span>  
  
```  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33f66-105">参数</span><span class="sxs-lookup"><span data-stu-id="33f66-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="33f66-106">[in] `ICorProfilerInfo*` 接口的接口指针。</span><span class="sxs-lookup"><span data-stu-id="33f66-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="33f66-107">[in]对数据的指针传递到[iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)中的方法及其`pvClientData`参数。</span><span class="sxs-lookup"><span data-stu-id="33f66-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="33f66-108">如果此参数为 NULL，则 `cbClientData` 将为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="33f66-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="33f66-109">当 CLR 从 `InitializeForAttach` 返回时将释放此内存。</span><span class="sxs-lookup"><span data-stu-id="33f66-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="33f66-110">[in] `pvClientData` 指向的数据的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="33f66-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33f66-111">备注</span><span class="sxs-lookup"><span data-stu-id="33f66-111">Remarks</span></span>  
 <span data-ttu-id="33f66-112">CLR 调用 `InitializeForAttach` 以便给予分析器请求回调的机会。</span><span class="sxs-lookup"><span data-stu-id="33f66-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33f66-113">要求</span><span class="sxs-lookup"><span data-stu-id="33f66-113">Requirements</span></span>  
 <span data-ttu-id="33f66-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33f66-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33f66-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33f66-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33f66-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33f66-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33f66-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33f66-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f66-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="33f66-118">See also</span></span>

- [<span data-ttu-id="33f66-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="33f66-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="33f66-120">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="33f66-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="33f66-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="33f66-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="33f66-122">分析</span><span class="sxs-lookup"><span data-stu-id="33f66-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
