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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebf72fe4f9fae5b3d791e6eed2e9421b9f4e3296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450812"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="9ac5e-102">ICorProfilerCallback::ClassUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="9ac5e-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="9ac5e-103">通知探查器已完成某个类的卸载。</span><span class="sxs-lookup"><span data-stu-id="9ac5e-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ac5e-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ac5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ac5e-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="9ac5e-106">[in]标识已卸载的类。</span><span class="sxs-lookup"><span data-stu-id="9ac5e-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9ac5e-107">[in]一个 HRESULT，指示是否已成功类已被卸载。</span><span class="sxs-lookup"><span data-stu-id="9ac5e-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ac5e-108">备注</span><span class="sxs-lookup"><span data-stu-id="9ac5e-108">Remarks</span></span>  
 <span data-ttu-id="9ac5e-109">卸载类的某些部分可能会继续之后`ClassUnloadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="9ac5e-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="9ac5e-110">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="9ac5e-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9ac5e-111">但是，HRESULT 为成功，在`hrStatus`仅指示已成功卸载类的第一部分。</span><span class="sxs-lookup"><span data-stu-id="9ac5e-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ac5e-112">要求</span><span class="sxs-lookup"><span data-stu-id="9ac5e-112">Requirements</span></span>  
 <span data-ttu-id="9ac5e-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ac5e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac5e-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ac5e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ac5e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ac5e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ac5e-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ac5e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac5e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ac5e-117">See Also</span></span>  
 [<span data-ttu-id="9ac5e-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9ac5e-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9ac5e-119">ClassUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="9ac5e-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
