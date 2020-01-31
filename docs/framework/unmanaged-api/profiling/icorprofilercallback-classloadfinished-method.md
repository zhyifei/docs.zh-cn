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
ms.openlocfilehash: e0ff90f99c1127b5a4626f47514ba7099b5d48af
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866593"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="11f76-102">ICorProfilerCallback::ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="11f76-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="11f76-103">通知探查器类已经完成加载。</span><span class="sxs-lookup"><span data-stu-id="11f76-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f76-104">语法</span><span class="sxs-lookup"><span data-stu-id="11f76-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11f76-105">参数</span><span class="sxs-lookup"><span data-stu-id="11f76-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="11f76-106">\[中的] 标识已加载的类。</span><span class="sxs-lookup"><span data-stu-id="11f76-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="11f76-107">\[中的] 表示是否已成功加载类的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="11f76-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="11f76-108">备注</span><span class="sxs-lookup"><span data-stu-id="11f76-108">Remarks</span></span>  
 <span data-ttu-id="11f76-109">在调用 `ClassLoadFinished` 方法之前，`classId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="11f76-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="11f76-110">在 `ClassLoadFinished` 回调后，加载类的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="11f76-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="11f76-111">如果 `hrStatus` 失败，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="11f76-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="11f76-112">不过，`hrStatus` 中的 HRESULT 成功仅指示加载类的第一部分已成功。</span><span class="sxs-lookup"><span data-stu-id="11f76-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11f76-113">需求</span><span class="sxs-lookup"><span data-stu-id="11f76-113">Requirements</span></span>  
 <span data-ttu-id="11f76-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11f76-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11f76-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11f76-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11f76-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11f76-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11f76-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11f76-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f76-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11f76-118">See also</span></span>

- [<span data-ttu-id="11f76-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="11f76-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="11f76-120">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="11f76-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
