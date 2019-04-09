---
title: ICorProfilerCallback::ClassLoadStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db7a033944272756a739dec39d4df11fde1d48b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178602"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="d37c7-102">ICorProfilerCallback::ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="d37c7-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="d37c7-103">通知探查器正在加载的类。</span><span class="sxs-lookup"><span data-stu-id="d37c7-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d37c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="d37c7-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d37c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="d37c7-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d37c7-106">[in]标识要加载的类。</span><span class="sxs-lookup"><span data-stu-id="d37c7-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d37c7-107">备注</span><span class="sxs-lookup"><span data-stu-id="d37c7-107">Remarks</span></span>  
 <span data-ttu-id="d37c7-108">值`classId`不是有效的信息请求之前[icorprofilercallback:: Classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="d37c7-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d37c7-109">要求</span><span class="sxs-lookup"><span data-stu-id="d37c7-109">Requirements</span></span>  
 <span data-ttu-id="d37c7-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d37c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d37c7-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d37c7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d37c7-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d37c7-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d37c7-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d37c7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d37c7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d37c7-114">See also</span></span>

- [<span data-ttu-id="d37c7-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d37c7-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
