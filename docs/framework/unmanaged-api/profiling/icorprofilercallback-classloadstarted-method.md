---
title: "ICorProfilerCallback::ClassLoadStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f1622fdbbeb1f200f996e49c432600165a029aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="cd676-102">ICorProfilerCallback::ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="cd676-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="cd676-103">通知探查器正在加载的类。</span><span class="sxs-lookup"><span data-stu-id="cd676-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd676-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd676-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd676-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd676-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cd676-106">[in]标识正在加载的类。</span><span class="sxs-lookup"><span data-stu-id="cd676-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd676-107">备注</span><span class="sxs-lookup"><span data-stu-id="cd676-107">Remarks</span></span>  
 <span data-ttu-id="cd676-108">值`classId`无效的信息请求之前，不能[icorprofilercallback:: Classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="cd676-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd676-109">要求</span><span class="sxs-lookup"><span data-stu-id="cd676-109">Requirements</span></span>  
 <span data-ttu-id="cd676-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd676-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd676-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd676-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd676-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd676-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd676-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd676-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd676-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd676-114">See Also</span></span>  
 [<span data-ttu-id="cd676-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="cd676-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
