---
title: ICorProfilerCallback::AssemblyLoadStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: b83be5e79c533e7e5a2468a12a0793d300700428
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866632"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="010e6-102">ICorProfilerCallback::AssemblyLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="010e6-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="010e6-103">通知探查器正在加载程序集。</span><span class="sxs-lookup"><span data-stu-id="010e6-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="010e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="010e6-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="010e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="010e6-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="010e6-106">\[中的] 标识要加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="010e6-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="010e6-107">备注</span><span class="sxs-lookup"><span data-stu-id="010e6-107">Remarks</span></span>  
 <span data-ttu-id="010e6-108">在调用[ICorProfilerCallback：： AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md)方法之前，`assemblyId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="010e6-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="010e6-109">需求</span><span class="sxs-lookup"><span data-stu-id="010e6-109">Requirements</span></span>  
 <span data-ttu-id="010e6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="010e6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="010e6-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="010e6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="010e6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="010e6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="010e6-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="010e6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="010e6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="010e6-114">See also</span></span>

- [<span data-ttu-id="010e6-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="010e6-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
