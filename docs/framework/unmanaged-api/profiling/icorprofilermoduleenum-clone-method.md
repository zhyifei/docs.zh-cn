---
title: ICorProfilerModuleEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9249e6f5ee7b15d55f5518263b0ac2e31b64e993
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454455"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="1164d-102">ICorProfilerModuleEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="1164d-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="1164d-103">获取对此副本的接口指针[ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1164d-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1164d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1164d-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1164d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1164d-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="1164d-106">[out]指向反过来指向此副本的接口指针的指针[ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1164d-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="1164d-107">枚举器的副本将保持独立于此枚举器自己枚举状态。</span><span class="sxs-lookup"><span data-stu-id="1164d-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="1164d-108">但是，该副本的初始光标位置是此枚举器的当前光标位置相同。</span><span class="sxs-lookup"><span data-stu-id="1164d-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1164d-109">要求</span><span class="sxs-lookup"><span data-stu-id="1164d-109">Requirements</span></span>  
 <span data-ttu-id="1164d-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1164d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1164d-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1164d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1164d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1164d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1164d-113">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1164d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1164d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1164d-114">See Also</span></span>  
 [<span data-ttu-id="1164d-115">ICorProfilerModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="1164d-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="1164d-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="1164d-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
