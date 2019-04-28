---
title: ICorProfilerCallback::ClassLoadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cab4b039d225f4ee1b00add6ffec63fd35be8857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597968"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="c949c-102">ICorProfilerCallback::ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="c949c-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="c949c-103">通知探查器加载已完成某个类。</span><span class="sxs-lookup"><span data-stu-id="c949c-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c949c-104">语法</span><span class="sxs-lookup"><span data-stu-id="c949c-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c949c-105">参数</span><span class="sxs-lookup"><span data-stu-id="c949c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c949c-106">[in]标识已加载的类。</span><span class="sxs-lookup"><span data-stu-id="c949c-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c949c-107">[in]一个 HRESULT，指示是否已成功加载的类。</span><span class="sxs-lookup"><span data-stu-id="c949c-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c949c-108">备注</span><span class="sxs-lookup"><span data-stu-id="c949c-108">Remarks</span></span>  
 <span data-ttu-id="c949c-109">值`classId`不是有效信息请求直到`ClassLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="c949c-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="c949c-110">加载类的某些部分可能会继续后`ClassLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="c949c-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="c949c-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="c949c-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c949c-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功加载类的第一部分。</span><span class="sxs-lookup"><span data-stu-id="c949c-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c949c-113">要求</span><span class="sxs-lookup"><span data-stu-id="c949c-113">Requirements</span></span>  
 <span data-ttu-id="c949c-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c949c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c949c-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c949c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c949c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c949c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c949c-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c949c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c949c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c949c-118">See also</span></span>

- [<span data-ttu-id="c949c-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c949c-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c949c-120">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="c949c-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
