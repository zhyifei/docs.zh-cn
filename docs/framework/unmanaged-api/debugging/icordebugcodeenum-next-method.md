---
title: ICorDebugCodeEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5db87cd4ad965654b63a68828cd088b8d2f7d07c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749782"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="68375-102">ICorDebugCodeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="68375-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="68375-103">从当前位置开始枚举中获取指定的数量的"ICorDebugCode"实例。</span><span class="sxs-lookup"><span data-stu-id="68375-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68375-104">语法</span><span class="sxs-lookup"><span data-stu-id="68375-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68375-105">参数</span><span class="sxs-lookup"><span data-stu-id="68375-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="68375-106">[in]数`ICorDebugCode`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="68375-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="68375-107">[out]一个指针，其中每个指向数组`ICorDebugCode`对象。</span><span class="sxs-lookup"><span data-stu-id="68375-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="68375-108">[out]指向数`ICorDebugCode`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="68375-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="68375-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="68375-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68375-110">要求</span><span class="sxs-lookup"><span data-stu-id="68375-110">Requirements</span></span>  
 <span data-ttu-id="68375-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68375-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68375-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68375-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68375-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68375-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68375-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68375-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68375-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="68375-115">See also</span></span>
