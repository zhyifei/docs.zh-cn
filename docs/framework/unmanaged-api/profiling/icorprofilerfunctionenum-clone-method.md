---
title: ICorProfilerFunctionEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e30cc8ff320c1a4a9a69fb2a07427ef4c8a4149
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485364"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="5d132-102">ICorProfilerFunctionEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="5d132-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="5d132-103">此副本中获取的接口指针[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5d132-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d132-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d132-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d132-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d132-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5d132-106">[out]指向指针的接口指针，用于又指向这份[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="5d132-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="5d132-107">枚举器的副本维护其自己的枚举状态独立于此枚举器。</span><span class="sxs-lookup"><span data-stu-id="5d132-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="5d132-108">但是，该副本的初始光标位置是与此枚举器的当前光标位置相同。</span><span class="sxs-lookup"><span data-stu-id="5d132-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d132-109">要求</span><span class="sxs-lookup"><span data-stu-id="5d132-109">Requirements</span></span>  
 <span data-ttu-id="5d132-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d132-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d132-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d132-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d132-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d132-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d132-113">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d132-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d132-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d132-114">See also</span></span>
- [<span data-ttu-id="5d132-115">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="5d132-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="5d132-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="5d132-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
