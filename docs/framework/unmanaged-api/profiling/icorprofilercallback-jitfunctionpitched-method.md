---
title: ICorProfilerCallback::JITFunctionPitched 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8aa46e869d50fc7aa65c1d4244ad4ff71657bad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186389"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="ee8dd-102">ICorProfilerCallback::JITFunctionPitched 方法</span><span class="sxs-lookup"><span data-stu-id="ee8dd-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="ee8dd-103">通知探查器的已实时 (JIT) 的函数的编译已从内存中删除。</span><span class="sxs-lookup"><span data-stu-id="ee8dd-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee8dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee8dd-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee8dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee8dd-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ee8dd-106">[in]已删除的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="ee8dd-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee8dd-107">备注</span><span class="sxs-lookup"><span data-stu-id="ee8dd-107">Remarks</span></span>  
 <span data-ttu-id="ee8dd-108">如果调用已删除的函数时，探查器会收到新的 JIT 编译事件时重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="ee8dd-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="ee8dd-109">目前，公共语言运行时 (CLR) JIT 编译器不会删除函数从内存，所以此回调当前未使用且不会收到探查器。</span><span class="sxs-lookup"><span data-stu-id="ee8dd-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="ee8dd-110">值`functionId`直到重新编译该函数不有效。</span><span class="sxs-lookup"><span data-stu-id="ee8dd-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="ee8dd-111">该函数重新编译时，相同`functionId`将使用的值。</span><span class="sxs-lookup"><span data-stu-id="ee8dd-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee8dd-112">要求</span><span class="sxs-lookup"><span data-stu-id="ee8dd-112">Requirements</span></span>  
 <span data-ttu-id="ee8dd-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee8dd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee8dd-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee8dd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee8dd-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee8dd-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ee8dd-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="ee8dd-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee8dd-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee8dd-117">See also</span></span>

- [<span data-ttu-id="ee8dd-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ee8dd-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
