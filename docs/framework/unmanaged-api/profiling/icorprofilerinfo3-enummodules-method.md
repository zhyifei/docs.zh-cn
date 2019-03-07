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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73218a5b63ae53ac125d3d807c1a50bdbf0d9c8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503055"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="7e620-102">ICorProfilerInfo3::EnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="7e620-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="7e620-103">返回一个枚举器，此枚举器提供方法以按顺序循环访问加载到应用程序的托管模块集合。</span><span class="sxs-lookup"><span data-stu-id="7e620-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e620-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e620-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e620-105">参数</span><span class="sxs-lookup"><span data-stu-id="7e620-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7e620-106">[out]一个指向[ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7e620-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e620-107">备注</span><span class="sxs-lookup"><span data-stu-id="7e620-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e620-108">要求</span><span class="sxs-lookup"><span data-stu-id="7e620-108">Requirements</span></span>  
 <span data-ttu-id="7e620-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e620-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e620-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e620-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e620-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e620-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e620-112">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e620-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e620-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e620-113">See also</span></span>
- [<span data-ttu-id="7e620-114">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="7e620-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="7e620-115">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="7e620-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="7e620-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="7e620-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="7e620-117">分析</span><span class="sxs-lookup"><span data-stu-id="7e620-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
