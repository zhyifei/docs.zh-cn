---
title: "ICorProfilerInfo3::EnumModules 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.EnumModules Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0215662439672aecc787530ceb68d16cc58bcc3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="33b75-102">ICorProfilerInfo3::EnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="33b75-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="33b75-103">返回一个枚举器，此枚举器提供方法以按顺序循环访问加载到应用程序的托管模块集合。</span><span class="sxs-lookup"><span data-stu-id="33b75-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b75-104">语法</span><span class="sxs-lookup"><span data-stu-id="33b75-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33b75-105">参数</span><span class="sxs-lookup"><span data-stu-id="33b75-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="33b75-106">[out]指向的指针[ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="33b75-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33b75-107">备注</span><span class="sxs-lookup"><span data-stu-id="33b75-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33b75-108">惠?</span><span class="sxs-lookup"><span data-stu-id="33b75-108">Requirements</span></span>  
 <span data-ttu-id="33b75-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33b75-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33b75-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33b75-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33b75-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33b75-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33b75-112">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33b75-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b75-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="33b75-113">See Also</span></span>  
 [<span data-ttu-id="33b75-114">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="33b75-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="33b75-115">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="33b75-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="33b75-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="33b75-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="33b75-117">分析</span><span class="sxs-lookup"><span data-stu-id="33b75-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
