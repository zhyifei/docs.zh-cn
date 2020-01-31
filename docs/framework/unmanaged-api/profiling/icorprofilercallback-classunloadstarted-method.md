---
title: ICorProfilerCallback::ClassUnloadStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 75fb92be078c40f49ddcdc6662535b2a0be7a6ad
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866554"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="99396-102">ICorProfilerCallback::ClassUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="99396-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="99396-103">通知探查器正在卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="99396-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99396-104">语法</span><span class="sxs-lookup"><span data-stu-id="99396-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99396-105">参数</span><span class="sxs-lookup"><span data-stu-id="99396-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="99396-106">\[中的] 标识正在卸载的类。</span><span class="sxs-lookup"><span data-stu-id="99396-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="99396-107">备注</span><span class="sxs-lookup"><span data-stu-id="99396-107">Remarks</span></span>  
 <span data-ttu-id="99396-108">`ClassUnloadStarted` 方法返回后，`classId` 的值对信息请求无效-这是探查器获取有关此类的信息的最后机会。</span><span class="sxs-lookup"><span data-stu-id="99396-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99396-109">需求</span><span class="sxs-lookup"><span data-stu-id="99396-109">Requirements</span></span>  
 <span data-ttu-id="99396-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99396-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99396-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99396-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99396-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99396-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99396-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99396-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99396-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99396-114">See also</span></span>

- [<span data-ttu-id="99396-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="99396-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="99396-116">ClassUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="99396-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
