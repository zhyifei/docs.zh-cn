---
title: ICorProfilerCallback::AssemblyUnloadStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: 0a677e33950f178b916a5e9e9cbb7bd918c1349b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866606"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="ae902-102">ICorProfilerCallback::AssemblyUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="ae902-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="ae902-103">通知探查器正在卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="ae902-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae902-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae902-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae902-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae902-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="ae902-106">\[中的] 标识正在卸载的程序集。</span><span class="sxs-lookup"><span data-stu-id="ae902-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae902-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae902-107">Remarks</span></span>  
 <span data-ttu-id="ae902-108">`AssemblyUnloadStarted` 方法返回后，`assemblyId` 的值对信息请求无效-这是探查器获取有关此程序集的相关信息的最后机会。</span><span class="sxs-lookup"><span data-stu-id="ae902-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae902-109">需求</span><span class="sxs-lookup"><span data-stu-id="ae902-109">Requirements</span></span>  
 <span data-ttu-id="ae902-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae902-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae902-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae902-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae902-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae902-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae902-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae902-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae902-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae902-114">See also</span></span>

- [<span data-ttu-id="ae902-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ae902-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ae902-116">AssemblyUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ae902-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
