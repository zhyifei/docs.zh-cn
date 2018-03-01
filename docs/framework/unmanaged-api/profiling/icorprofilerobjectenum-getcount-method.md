---
title: "ICorProfilerObjectEnum::GetCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7675749a132cffe284d73bab3dba91f6ff7a3fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="0ea8c-102">ICorProfilerObjectEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="0ea8c-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="0ea8c-103">获取集合中的已冻结对象总数。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ea8c-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ea8c-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ea8c-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="0ea8c-106">[out]指向集合中的已冻结对象数的指针。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="0ea8c-107">此方法将始终返回零.NET Framework 版本 3.5 Service Pack 1 (SP1) 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ea8c-108">惠?</span><span class="sxs-lookup"><span data-stu-id="0ea8c-108">Requirements</span></span>  
 <span data-ttu-id="0ea8c-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea8c-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ea8c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ea8c-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ea8c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ea8c-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea8c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea8c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ea8c-113">See Also</span></span>  
 [<span data-ttu-id="0ea8c-114">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="0ea8c-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
