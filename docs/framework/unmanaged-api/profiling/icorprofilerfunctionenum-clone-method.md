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
ms.openlocfilehash: ded15608337d040ab58cb5be45deac4711668ac3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576169"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="4e635-102">ICorProfilerFunctionEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="4e635-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="4e635-103">此副本中获取的接口指针[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="4e635-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e635-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e635-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e635-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e635-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4e635-106">[out]指向指针的接口指针，用于又指向这份[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="4e635-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="4e635-107">枚举器的副本维护其自己的枚举状态独立于此枚举器。</span><span class="sxs-lookup"><span data-stu-id="4e635-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="4e635-108">但是，该副本的初始光标位置是与此枚举器的当前光标位置相同。</span><span class="sxs-lookup"><span data-stu-id="4e635-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e635-109">要求</span><span class="sxs-lookup"><span data-stu-id="4e635-109">Requirements</span></span>  
 <span data-ttu-id="4e635-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e635-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e635-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e635-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e635-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e635-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e635-113">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e635-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e635-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e635-114">See also</span></span>
- [<span data-ttu-id="4e635-115">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4e635-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="4e635-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="4e635-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
