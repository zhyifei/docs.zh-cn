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
ms.openlocfilehash: 33b72c8d089e5b335069fe465987086dfa1243bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445170"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="bf978-102">ICorProfilerCallback::AssemblyLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="bf978-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="bf978-103">Notifies the profiler that an assembly has finished loading.</span><span class="sxs-lookup"><span data-stu-id="bf978-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf978-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf978-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf978-105">参数</span><span class="sxs-lookup"><span data-stu-id="bf978-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="bf978-106">[in] Identifies the assembly that was loaded.</span><span class="sxs-lookup"><span data-stu-id="bf978-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bf978-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span><span class="sxs-lookup"><span data-stu-id="bf978-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf978-108">备注</span><span class="sxs-lookup"><span data-stu-id="bf978-108">Remarks</span></span>  
 <span data-ttu-id="bf978-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span><span class="sxs-lookup"><span data-stu-id="bf978-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="bf978-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="bf978-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="bf978-111">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="bf978-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bf978-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span><span class="sxs-lookup"><span data-stu-id="bf978-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf978-113">要求</span><span class="sxs-lookup"><span data-stu-id="bf978-113">Requirements</span></span>  
 <span data-ttu-id="bf978-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf978-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf978-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf978-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf978-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf978-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf978-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf978-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf978-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf978-118">See also</span></span>

- [<span data-ttu-id="bf978-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="bf978-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
