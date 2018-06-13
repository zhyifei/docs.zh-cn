---
title: ICorProfilerObjectEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e8a623107e5e03ca36137c253c9bdf0a722d385
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456031"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="e0073-102">ICorProfilerObjectEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="e0073-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="e0073-103">获取对此副本的接口指针[ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e0073-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0073-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0073-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0073-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0073-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e0073-106">[out]指向反过来指向此副本的接口指针的指针`ICorProfilerObjectEnum`接口。</span><span class="sxs-lookup"><span data-stu-id="e0073-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="e0073-107">复制维护其自己的枚举状态独立于此。</span><span class="sxs-lookup"><span data-stu-id="e0073-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="e0073-108">但是，该副本的初始光标位置将与此枚举器的当前光标位置相同。</span><span class="sxs-lookup"><span data-stu-id="e0073-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0073-109">要求</span><span class="sxs-lookup"><span data-stu-id="e0073-109">Requirements</span></span>  
 <span data-ttu-id="e0073-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0073-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0073-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0073-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0073-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0073-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0073-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0073-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0073-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0073-114">See Also</span></span>  
 [<span data-ttu-id="e0073-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e0073-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
