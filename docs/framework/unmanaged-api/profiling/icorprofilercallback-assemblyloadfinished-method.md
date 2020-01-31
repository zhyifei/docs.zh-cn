---
title: ICorProfilerCallback::AssemblyLoadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: 15ce195af0c0e8f8777f6e5d02043e17e32308da
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866638"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="9bda0-102">ICorProfilerCallback::AssemblyLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="9bda0-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="9bda0-103">通知探查器程序集已完成加载。</span><span class="sxs-lookup"><span data-stu-id="9bda0-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bda0-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bda0-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bda0-105">参数</span><span class="sxs-lookup"><span data-stu-id="9bda0-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="9bda0-106">\[中的] 标识已加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="9bda0-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="9bda0-107">\[中的] HRESULT，指示程序集是否已成功加载。</span><span class="sxs-lookup"><span data-stu-id="9bda0-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="9bda0-108">备注</span><span class="sxs-lookup"><span data-stu-id="9bda0-108">Remarks</span></span>  
 <span data-ttu-id="9bda0-109">在调用 `AssemblyLoadFinished` 方法之前，`assemblyId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="9bda0-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="9bda0-110">在 `AssemblyLoadFinished` 回调后，加载程序集的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="9bda0-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="9bda0-111">如果 `hrStatus` 失败，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="9bda0-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9bda0-112">不过，`hrStatus` 中的 HRESULT 成功只指示加载程序集的第一部分已成功完成。</span><span class="sxs-lookup"><span data-stu-id="9bda0-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bda0-113">需求</span><span class="sxs-lookup"><span data-stu-id="9bda0-113">Requirements</span></span>  
 <span data-ttu-id="9bda0-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9bda0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bda0-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9bda0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9bda0-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bda0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bda0-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bda0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bda0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bda0-118">See also</span></span>

- [<span data-ttu-id="9bda0-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9bda0-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
