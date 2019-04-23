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
ms.openlocfilehash: 9d01f3d7485b19c076d9cd3e83aeccbcf5e728f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160701"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="49423-102">ICorProfilerCallback::ClassUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="49423-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="49423-103">通知探查器类已完成卸载。</span><span class="sxs-lookup"><span data-stu-id="49423-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49423-104">语法</span><span class="sxs-lookup"><span data-stu-id="49423-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49423-105">参数</span><span class="sxs-lookup"><span data-stu-id="49423-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="49423-106">[in]标识已被卸载的类。</span><span class="sxs-lookup"><span data-stu-id="49423-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="49423-107">[in]一个 HRESULT，指示是否已成功类已被卸载。</span><span class="sxs-lookup"><span data-stu-id="49423-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49423-108">备注</span><span class="sxs-lookup"><span data-stu-id="49423-108">Remarks</span></span>  
 <span data-ttu-id="49423-109">卸载类的某些部分可能会继续后`ClassUnloadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="49423-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="49423-110">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="49423-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="49423-111">但是，成功的 HRESULT 在`hrStatus`仅表示已成功卸载类的第一部分。</span><span class="sxs-lookup"><span data-stu-id="49423-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49423-112">要求</span><span class="sxs-lookup"><span data-stu-id="49423-112">Requirements</span></span>  
 <span data-ttu-id="49423-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49423-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49423-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49423-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49423-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49423-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49423-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49423-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49423-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="49423-117">See also</span></span>

- [<span data-ttu-id="49423-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="49423-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="49423-119">ClassUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="49423-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
