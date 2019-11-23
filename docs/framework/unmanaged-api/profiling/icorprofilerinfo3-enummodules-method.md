---
title: ICorProfilerInfo3::EnumModules 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
ms.openlocfilehash: 0bb2ba56ed93af7861e53d683a0a777107578a6b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449752"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="b05dd-102">ICorProfilerInfo3::EnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="b05dd-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="b05dd-103">返回一个枚举器，此枚举器提供方法以按顺序循环访问加载到应用程序的托管模块集合。</span><span class="sxs-lookup"><span data-stu-id="b05dd-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b05dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="b05dd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b05dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="b05dd-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b05dd-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="b05dd-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b05dd-107">备注</span><span class="sxs-lookup"><span data-stu-id="b05dd-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b05dd-108">要求</span><span class="sxs-lookup"><span data-stu-id="b05dd-108">Requirements</span></span>  
 <span data-ttu-id="b05dd-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b05dd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b05dd-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b05dd-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b05dd-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b05dd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b05dd-112">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b05dd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05dd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b05dd-113">See also</span></span>

- [<span data-ttu-id="b05dd-114">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b05dd-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="b05dd-115">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="b05dd-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b05dd-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="b05dd-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b05dd-117">分析</span><span class="sxs-lookup"><span data-stu-id="b05dd-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
