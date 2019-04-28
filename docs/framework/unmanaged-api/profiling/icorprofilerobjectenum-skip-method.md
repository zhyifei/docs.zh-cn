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
ms.openlocfilehash: 2bcc837fede7e7db59bdf88a0b5434a7c1924335
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597099"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="ccfbe-102">ICorProfilerObjectEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="ccfbe-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="ccfbe-103">因此跳过指定的数量的元素，请从其当前位置前移此枚举器的光标。</span><span class="sxs-lookup"><span data-stu-id="ccfbe-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfbe-104">语法</span><span class="sxs-lookup"><span data-stu-id="ccfbe-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccfbe-105">参数</span><span class="sxs-lookup"><span data-stu-id="ccfbe-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ccfbe-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="ccfbe-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccfbe-107">备注</span><span class="sxs-lookup"><span data-stu-id="ccfbe-107">Remarks</span></span>  
 <span data-ttu-id="ccfbe-108">此枚举器的光标的新位置是: （当前位置） + `celt` 。</span><span class="sxs-lookup"><span data-stu-id="ccfbe-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccfbe-109">要求</span><span class="sxs-lookup"><span data-stu-id="ccfbe-109">Requirements</span></span>  
 <span data-ttu-id="ccfbe-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ccfbe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccfbe-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ccfbe-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ccfbe-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccfbe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccfbe-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccfbe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfbe-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccfbe-114">See also</span></span>

- [<span data-ttu-id="ccfbe-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ccfbe-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
