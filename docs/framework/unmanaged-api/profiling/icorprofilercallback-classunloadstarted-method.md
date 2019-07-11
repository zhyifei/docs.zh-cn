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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a305835651867a533e17f1c5c3b85b16975c3b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745392"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="cb4aa-102">ICorProfilerCallback::ClassUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="cb4aa-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="cb4aa-103">通知探查器卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="cb4aa-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb4aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb4aa-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb4aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb4aa-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cb4aa-106">[in]标识正在卸载的类。</span><span class="sxs-lookup"><span data-stu-id="cb4aa-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb4aa-107">备注</span><span class="sxs-lookup"><span data-stu-id="cb4aa-107">Remarks</span></span>  
 <span data-ttu-id="cb4aa-108">值`classId`不是有效的信息请求后`ClassUnloadStarted`方法将返回-这是探查器的最后一次机会来获取有关此类信息。</span><span class="sxs-lookup"><span data-stu-id="cb4aa-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb4aa-109">要求</span><span class="sxs-lookup"><span data-stu-id="cb4aa-109">Requirements</span></span>  
 <span data-ttu-id="cb4aa-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb4aa-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb4aa-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb4aa-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb4aa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb4aa-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb4aa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4aa-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb4aa-114">See also</span></span>

- [<span data-ttu-id="cb4aa-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="cb4aa-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cb4aa-116">ClassUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="cb4aa-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
