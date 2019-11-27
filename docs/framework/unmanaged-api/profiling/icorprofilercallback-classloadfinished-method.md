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
ms.openlocfilehash: ef2c518f8f3f3069e93f06de89add1385cb4e45e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445117"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="65683-102">ICorProfilerCallback::ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="65683-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="65683-103">通知探查器类已经完成加载。</span><span class="sxs-lookup"><span data-stu-id="65683-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65683-104">语法</span><span class="sxs-lookup"><span data-stu-id="65683-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65683-105">参数</span><span class="sxs-lookup"><span data-stu-id="65683-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="65683-106">中标识已加载的类。</span><span class="sxs-lookup"><span data-stu-id="65683-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="65683-107">中一个 HRESULT，指示类是否已成功加载。</span><span class="sxs-lookup"><span data-stu-id="65683-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65683-108">备注</span><span class="sxs-lookup"><span data-stu-id="65683-108">Remarks</span></span>  
 <span data-ttu-id="65683-109">在调用 `ClassLoadFinished` 方法之前，`classId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="65683-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="65683-110">在 `ClassLoadFinished` 回调后，加载类的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="65683-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="65683-111">如果 `hrStatus` 失败，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="65683-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="65683-112">不过，`hrStatus` 中的 HRESULT 成功仅指示加载类的第一部分已成功。</span><span class="sxs-lookup"><span data-stu-id="65683-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65683-113">要求</span><span class="sxs-lookup"><span data-stu-id="65683-113">Requirements</span></span>  
 <span data-ttu-id="65683-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65683-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65683-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65683-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65683-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65683-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65683-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65683-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65683-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65683-118">See also</span></span>

- [<span data-ttu-id="65683-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="65683-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="65683-120">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="65683-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
