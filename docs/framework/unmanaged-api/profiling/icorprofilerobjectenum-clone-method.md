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
ms.openlocfilehash: 14e8086532eff5dba6883575cc2daf447a32343a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182359"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="05cc6-102">ICorProfilerObjectEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="05cc6-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="05cc6-103">此副本中获取的接口指针[ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="05cc6-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05cc6-104">语法</span><span class="sxs-lookup"><span data-stu-id="05cc6-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05cc6-105">参数</span><span class="sxs-lookup"><span data-stu-id="05cc6-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="05cc6-106">[out]又指向此副本的接口指针的指针`ICorProfilerObjectEnum`接口。</span><span class="sxs-lookup"><span data-stu-id="05cc6-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="05cc6-107">复制维护其自己的枚举状态独立于此。</span><span class="sxs-lookup"><span data-stu-id="05cc6-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="05cc6-108">但是，该副本的初始游标位置将与此枚举器的当前光标位置相同。</span><span class="sxs-lookup"><span data-stu-id="05cc6-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05cc6-109">要求</span><span class="sxs-lookup"><span data-stu-id="05cc6-109">Requirements</span></span>  
 <span data-ttu-id="05cc6-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05cc6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05cc6-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05cc6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05cc6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05cc6-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="05cc6-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="05cc6-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05cc6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="05cc6-114">See also</span></span>

- [<span data-ttu-id="05cc6-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="05cc6-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
