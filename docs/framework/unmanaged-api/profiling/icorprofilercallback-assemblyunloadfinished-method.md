---
title: ICorProfilerCallback::AssemblyUnloadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 734ae1d14d02d47c7d3126f1b4cf55dcb4ad151b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866619"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="2aaee-102">ICorProfilerCallback::AssemblyUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="2aaee-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="2aaee-103">通知探查器已卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="2aaee-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aaee-104">语法</span><span class="sxs-lookup"><span data-stu-id="2aaee-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aaee-105">参数</span><span class="sxs-lookup"><span data-stu-id="2aaee-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="2aaee-106">\[中的] 标识正在卸载的程序集。</span><span class="sxs-lookup"><span data-stu-id="2aaee-106">\[in] Identifies the assembly that is being unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="2aaee-107">\[中的] HRESULT，它指示是否已成功卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="2aaee-107">\[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="2aaee-108">备注</span><span class="sxs-lookup"><span data-stu-id="2aaee-108">Remarks</span></span>  
 <span data-ttu-id="2aaee-109">[ICorProfilerCallback：： AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md)方法返回后，`assemblyId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="2aaee-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="2aaee-110">在 `AssemblyUnloadFinished` 回调后，卸载程序集的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="2aaee-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="2aaee-111">如果 `hrStatus` 失败，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="2aaee-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2aaee-112">不过，`hrStatus` 中的 HRESULT 成功只指示卸载程序集的第一部分已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2aaee-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aaee-113">需求</span><span class="sxs-lookup"><span data-stu-id="2aaee-113">Requirements</span></span>  
 <span data-ttu-id="2aaee-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2aaee-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aaee-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2aaee-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2aaee-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2aaee-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2aaee-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aaee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aaee-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2aaee-118">See also</span></span>

- [<span data-ttu-id="2aaee-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2aaee-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
