---
title: "ICorDebugCodeEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCodeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dbc7985ebf2fff5fa0c5b524b8d6560f75318d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="0e874-102">ICorDebugCodeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="0e874-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="0e874-103">获取指定的数量的"icor 调试代码"实例的枚举，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="0e874-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e874-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e874-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e874-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e874-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0e874-106">[in]数`ICorDebugCode`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="0e874-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="0e874-107">[out]一个指针，其中每个指向数组`ICorDebugCode`对象。</span><span class="sxs-lookup"><span data-stu-id="0e874-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0e874-108">[out]指向数`ICorDebugCode`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="0e874-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="0e874-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="0e874-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e874-110">惠?</span><span class="sxs-lookup"><span data-stu-id="0e874-110">Requirements</span></span>  
 <span data-ttu-id="0e874-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e874-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e874-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e874-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e874-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e874-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e874-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e874-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e874-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e874-115">See Also</span></span>  
    
 
