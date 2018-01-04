---
title: "ICorProfilerCallback::ClassLoadFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae55325f514f9bec3efdf4764958e4b3fafd922b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="f9106-102">ICorProfilerCallback::ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="f9106-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="f9106-103">通知探查器加载已完成某个类。</span><span class="sxs-lookup"><span data-stu-id="f9106-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9106-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9106-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9106-105">参数</span><span class="sxs-lookup"><span data-stu-id="f9106-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f9106-106">[in]标识已加载的类。</span><span class="sxs-lookup"><span data-stu-id="f9106-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="f9106-107">[in]一个 HRESULT，指示类是否成功加载。</span><span class="sxs-lookup"><span data-stu-id="f9106-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9106-108">备注</span><span class="sxs-lookup"><span data-stu-id="f9106-108">Remarks</span></span>  
 <span data-ttu-id="f9106-109">值`classId`无效的信息请求之前，不能`ClassLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="f9106-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="f9106-110">加载类的某些部分可能会继续之后`ClassLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="f9106-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="f9106-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="f9106-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="f9106-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功加载类的第一部分。</span><span class="sxs-lookup"><span data-stu-id="f9106-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9106-113">惠?</span><span class="sxs-lookup"><span data-stu-id="f9106-113">Requirements</span></span>  
 <span data-ttu-id="f9106-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9106-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9106-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9106-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9106-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9106-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9106-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9106-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9106-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9106-118">See Also</span></span>  
 [<span data-ttu-id="f9106-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f9106-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f9106-120">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="f9106-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
