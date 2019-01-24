---
title: ICorProfilerCallback4::ReJITError 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b77dcbb1acffe47524aee3cd7761e342175dcd34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733684"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="ad346-102">ICorProfilerCallback4::ReJITError 方法</span><span class="sxs-lookup"><span data-stu-id="ad346-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="ad346-103">通知探查器在实时 (JIT) 编译器时重新编译过程中的出错。</span><span class="sxs-lookup"><span data-stu-id="ad346-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad346-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad346-104">Syntax</span></span>  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad346-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad346-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="ad346-106">[in]`ModuleID`中进行重新编译失败的尝试。</span><span class="sxs-lookup"><span data-stu-id="ad346-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="ad346-107">[in]`MethodDef`在其上进行了重新编译失败的尝试的方法。</span><span class="sxs-lookup"><span data-stu-id="ad346-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="ad346-108">[in]正在重新编译或已标记为重新编译函数实例。</span><span class="sxs-lookup"><span data-stu-id="ad346-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="ad346-109">此值可能为`NULL`如果而不是实例化每个安装在每个方法的基础上发生故障 （例如，如果探查器指定要重新编译的方法的无效的元数据令牌）。</span><span class="sxs-lookup"><span data-stu-id="ad346-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ad346-110">[in]一个 HRESULT，指示故障的性质。</span><span class="sxs-lookup"><span data-stu-id="ad346-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="ad346-111">请参阅值的列表的状态 HRESULT 部分。</span><span class="sxs-lookup"><span data-stu-id="ad346-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad346-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ad346-112">Return Value</span></span>  
 <span data-ttu-id="ad346-113">将忽略此回调的返回值。</span><span class="sxs-lookup"><span data-stu-id="ad346-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="ad346-114">状态 HRESULTS</span><span class="sxs-lookup"><span data-stu-id="ad346-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="ad346-115">状态数组 HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad346-115">Status array HRESULT</span></span>|<span data-ttu-id="ad346-116">描述</span><span class="sxs-lookup"><span data-stu-id="ad346-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="ad346-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ad346-117">E_INVALIDARG</span></span>|<span data-ttu-id="ad346-118">`moduleID`或`methodDef`令牌是`NULL`。</span><span class="sxs-lookup"><span data-stu-id="ad346-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="ad346-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="ad346-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="ad346-120">该模块尚未完全加载，或正在被卸载。</span><span class="sxs-lookup"><span data-stu-id="ad346-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="ad346-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="ad346-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="ad346-122">动态生成指定的模块 (例如，通过`Reflection.Emit`)，并因此不受此方法。</span><span class="sxs-lookup"><span data-stu-id="ad346-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="ad346-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="ad346-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="ad346-124">该方法在可回收程序集，实例化，并因此不能重新编译。</span><span class="sxs-lookup"><span data-stu-id="ad346-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="ad346-125">请注意，类型和非反射上下文中定义的函数 (例如， `List<MyCollectibleStruct>`) 可以实例化成可回收程序集。</span><span class="sxs-lookup"><span data-stu-id="ad346-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="ad346-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ad346-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ad346-127">尝试将标记为 JIT 重新编译指定的方法时 CLR 内存不足。</span><span class="sxs-lookup"><span data-stu-id="ad346-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="ad346-128">其他</span><span class="sxs-lookup"><span data-stu-id="ad346-128">Other</span></span>|<span data-ttu-id="ad346-129">操作系统返回了 CLR 控件范围之外的失败。</span><span class="sxs-lookup"><span data-stu-id="ad346-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="ad346-130">例如，如果要更改的内存页的访问权限保护的系统调用失败，将显示操作系统错误。</span><span class="sxs-lookup"><span data-stu-id="ad346-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad346-131">要求</span><span class="sxs-lookup"><span data-stu-id="ad346-131">Requirements</span></span>  
 <span data-ttu-id="ad346-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad346-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad346-133">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad346-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad346-134">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad346-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad346-135">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad346-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad346-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad346-136">See also</span></span>
- [<span data-ttu-id="ad346-137">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ad346-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ad346-138">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="ad346-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
