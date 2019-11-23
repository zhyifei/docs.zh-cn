---
title: ICorProfilerObjectEnum::GetCount 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 077e6d729eb98ddad25cd0c0cccf6d4641e2602c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428255"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="aada3-102">ICorProfilerObjectEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="aada3-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="aada3-103">Gets the total number of frozen objects in the collection.</span><span class="sxs-lookup"><span data-stu-id="aada3-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aada3-104">语法</span><span class="sxs-lookup"><span data-stu-id="aada3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aada3-105">参数</span><span class="sxs-lookup"><span data-stu-id="aada3-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="aada3-106">[out] A pointer to the number of frozen objects in the collection.</span><span class="sxs-lookup"><span data-stu-id="aada3-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="aada3-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span><span class="sxs-lookup"><span data-stu-id="aada3-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aada3-108">要求</span><span class="sxs-lookup"><span data-stu-id="aada3-108">Requirements</span></span>  
 <span data-ttu-id="aada3-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aada3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aada3-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aada3-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aada3-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aada3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aada3-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aada3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aada3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="aada3-113">See also</span></span>

- [<span data-ttu-id="aada3-114">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="aada3-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
