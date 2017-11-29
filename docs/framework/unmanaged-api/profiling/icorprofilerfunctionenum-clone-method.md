---
title: "ICorProfilerFunctionEnum::Clone 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Clone Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dc1d14a1480c3634993190448f9beff911bebf6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="b417c-102">ICorProfilerFunctionEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="b417c-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="b417c-103">获取对此副本的接口指针[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b417c-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b417c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b417c-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b417c-105">参数</span><span class="sxs-lookup"><span data-stu-id="b417c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b417c-106">[out]指向指针的接口指针，用于，反过来，指向这份[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b417c-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="b417c-107">枚举器的副本将保持独立于此枚举器自己枚举状态。</span><span class="sxs-lookup"><span data-stu-id="b417c-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="b417c-108">但是，该副本的初始光标位置是此枚举器的当前光标位置相同。</span><span class="sxs-lookup"><span data-stu-id="b417c-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b417c-109">要求</span><span class="sxs-lookup"><span data-stu-id="b417c-109">Requirements</span></span>  
 <span data-ttu-id="b417c-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b417c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b417c-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b417c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b417c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b417c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b417c-113">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b417c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b417c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b417c-114">See Also</span></span>  
 [<span data-ttu-id="b417c-115">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b417c-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="b417c-116">分析接口</span><span class="sxs-lookup"><span data-stu-id="b417c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
