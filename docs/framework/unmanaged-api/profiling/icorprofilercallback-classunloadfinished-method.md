---
title: ICorProfilerCallback::ClassUnloadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: b78d604a28ffe01000a763f7e0dd3c1630e2c186
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435922"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="46098-102">ICorProfilerCallback::ClassUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="46098-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="46098-103">Notifies the profiler that a class has finished unloading.</span><span class="sxs-lookup"><span data-stu-id="46098-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46098-104">语法</span><span class="sxs-lookup"><span data-stu-id="46098-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46098-105">参数</span><span class="sxs-lookup"><span data-stu-id="46098-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="46098-106">[in] Identifies the class that was unloaded.</span><span class="sxs-lookup"><span data-stu-id="46098-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="46098-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span><span class="sxs-lookup"><span data-stu-id="46098-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46098-108">备注</span><span class="sxs-lookup"><span data-stu-id="46098-108">Remarks</span></span>  
 <span data-ttu-id="46098-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="46098-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="46098-110">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="46098-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="46098-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span><span class="sxs-lookup"><span data-stu-id="46098-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46098-112">要求</span><span class="sxs-lookup"><span data-stu-id="46098-112">Requirements</span></span>  
 <span data-ttu-id="46098-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46098-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46098-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46098-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46098-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46098-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46098-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46098-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46098-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="46098-117">See also</span></span>

- [<span data-ttu-id="46098-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="46098-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="46098-119">ClassUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="46098-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
