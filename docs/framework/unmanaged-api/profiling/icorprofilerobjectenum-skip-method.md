---
title: ICorProfilerObjectEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fe35757d895fef3c6267c671f3a91fc50df620a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455675"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="7fef6-102">ICorProfilerObjectEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="7fef6-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="7fef6-103">因此，跳过指定的数量的元素，请从其当前位置前移此枚举器的光标。</span><span class="sxs-lookup"><span data-stu-id="7fef6-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fef6-104">语法</span><span class="sxs-lookup"><span data-stu-id="7fef6-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fef6-105">参数</span><span class="sxs-lookup"><span data-stu-id="7fef6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7fef6-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="7fef6-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fef6-107">备注</span><span class="sxs-lookup"><span data-stu-id="7fef6-107">Remarks</span></span>  
 <span data-ttu-id="7fef6-108">此枚举器的光标的新位置是: （当前位置） + `celt` 。</span><span class="sxs-lookup"><span data-stu-id="7fef6-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fef6-109">要求</span><span class="sxs-lookup"><span data-stu-id="7fef6-109">Requirements</span></span>  
 <span data-ttu-id="7fef6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7fef6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fef6-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7fef6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7fef6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fef6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fef6-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fef6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fef6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fef6-114">See Also</span></span>  
 [<span data-ttu-id="7fef6-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="7fef6-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
