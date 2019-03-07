---
title: ICorDebugModuleEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027c7b0b9ee7902c81b620549b335cd123d8b277
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491368"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="06d68-102">ICorDebugModuleEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="06d68-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="06d68-103">获取由指定的"icor 调试模块"实例数`celt`枚举，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="06d68-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d68-104">语法</span><span class="sxs-lookup"><span data-stu-id="06d68-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06d68-105">参数</span><span class="sxs-lookup"><span data-stu-id="06d68-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="06d68-106">[in]数`ICorDebugModule`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="06d68-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="06d68-107">[out]一个指针，其中每个指向数组`ICorDebugModule`对象。</span><span class="sxs-lookup"><span data-stu-id="06d68-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="06d68-108">[out]指向数`ICorDebugModule`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="06d68-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="06d68-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="06d68-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d68-110">要求</span><span class="sxs-lookup"><span data-stu-id="06d68-110">Requirements</span></span>  
 <span data-ttu-id="06d68-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06d68-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d68-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06d68-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06d68-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06d68-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06d68-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d68-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d68-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="06d68-115">See also</span></span>

