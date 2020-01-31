---
title: ICorProfilerCallback::ModuleAttachedToAssembly 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: cb342b1c328daca5b3cfc0440e6f276ae54e3ed8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866177"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="dbb90-102">ICorProfilerCallback::ModuleAttachedToAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="dbb90-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="dbb90-103">通知探查器模块正在附加到其父程序集。</span><span class="sxs-lookup"><span data-stu-id="dbb90-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb90-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbb90-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbb90-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbb90-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="dbb90-106">中要附加的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="dbb90-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="dbb90-107">中模块附加到的父程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="dbb90-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbb90-108">备注</span><span class="sxs-lookup"><span data-stu-id="dbb90-108">Remarks</span></span>  
 <span data-ttu-id="dbb90-109">可以通过导入地址表（IAT）通过调用 `LoadLibrary`或元数据引用来加载模块。</span><span class="sxs-lookup"><span data-stu-id="dbb90-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="dbb90-110">因此，公共语言运行时（CLR）加载程序具有多个用于确定模块所在程序集的代码路径。</span><span class="sxs-lookup"><span data-stu-id="dbb90-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="dbb90-111">因此，在调用[ICorProfilerCallback：： ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)后，模块并不知道它所在的程序集，因此无法获取父程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="dbb90-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="dbb90-112">当模块附加到其父程序集并且可以获得其父程序集 ID 时，将调用 `ModuleAttachedToAssembly` 方法。</span><span class="sxs-lookup"><span data-stu-id="dbb90-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb90-113">需求</span><span class="sxs-lookup"><span data-stu-id="dbb90-113">Requirements</span></span>  
 <span data-ttu-id="dbb90-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb90-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb90-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dbb90-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dbb90-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbb90-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbb90-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbb90-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb90-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbb90-118">See also</span></span>

- [<span data-ttu-id="dbb90-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="dbb90-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
