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
ms.openlocfilehash: f3f321849c62ffd653ffa174ff91447a2c8eec73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="9e63f-102">ICorProfilerCallback::ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="9e63f-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="9e63f-103">通知探查器加载已完成某个类。</span><span class="sxs-lookup"><span data-stu-id="9e63f-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e63f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e63f-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e63f-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e63f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="9e63f-106">[in]标识已加载的类。</span><span class="sxs-lookup"><span data-stu-id="9e63f-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9e63f-107">[in]一个 HRESULT，指示类是否成功加载。</span><span class="sxs-lookup"><span data-stu-id="9e63f-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e63f-108">备注</span><span class="sxs-lookup"><span data-stu-id="9e63f-108">Remarks</span></span>  
 <span data-ttu-id="9e63f-109">值`classId`无效的信息请求之前，不能`ClassLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="9e63f-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="9e63f-110">加载类的某些部分可能会继续之后`ClassLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="9e63f-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="9e63f-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="9e63f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9e63f-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功加载类的第一部分。</span><span class="sxs-lookup"><span data-stu-id="9e63f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e63f-113">要求</span><span class="sxs-lookup"><span data-stu-id="9e63f-113">Requirements</span></span>  
 <span data-ttu-id="9e63f-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e63f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e63f-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e63f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e63f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e63f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e63f-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e63f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e63f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e63f-118">See Also</span></span>  
 [<span data-ttu-id="9e63f-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9e63f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9e63f-120">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="9e63f-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
