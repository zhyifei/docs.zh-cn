---
title: "ICorProfilerCallback::ClassUnloadStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 994fe840f728b244e5a6e6c83c03340961c30413
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="ea234-102">ICorProfilerCallback::ClassUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="ea234-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="ea234-103">通知探查器正在卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="ea234-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea234-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea234-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea234-105">参数</span><span class="sxs-lookup"><span data-stu-id="ea234-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ea234-106">[in]标识正在卸载的类。</span><span class="sxs-lookup"><span data-stu-id="ea234-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea234-107">备注</span><span class="sxs-lookup"><span data-stu-id="ea234-107">Remarks</span></span>  
 <span data-ttu-id="ea234-108">值`classId`无效的信息请求后，不能`ClassUnloadStarted`方法返回-这是探查器的最后一次机会，以获取有关此类信息。</span><span class="sxs-lookup"><span data-stu-id="ea234-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea234-109">惠?</span><span class="sxs-lookup"><span data-stu-id="ea234-109">Requirements</span></span>  
 <span data-ttu-id="ea234-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea234-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea234-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea234-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea234-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea234-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea234-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea234-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea234-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea234-114">See Also</span></span>  
 [<span data-ttu-id="ea234-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ea234-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ea234-116">ClassUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ea234-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
