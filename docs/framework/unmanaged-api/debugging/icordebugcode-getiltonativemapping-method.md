---
title: "ICorDebugCode::GetILToNativeMapping 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetILToNativeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4477ff22d08d5f7ef291c27c00b8985f89ebebd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="08552-102">ICorDebugCode::GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="08552-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="08552-103">获取表示 microsoft 中间语言 (MSIL) 偏移量到本机偏移量的映射的"COR_DEBUG_IL_TO_NATIVE_MAP"实例的数组。</span><span class="sxs-lookup"><span data-stu-id="08552-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08552-104">语法</span><span class="sxs-lookup"><span data-stu-id="08552-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08552-105">参数</span><span class="sxs-lookup"><span data-stu-id="08552-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="08552-106">[in] `map` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="08552-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="08552-107">[out]指向元素中返回的实际数目`map`数组。</span><span class="sxs-lookup"><span data-stu-id="08552-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="08552-108">[out]数组`COR_DEBUG_IL_TO_NATIVE_MAP`结构，其中每个表示从 MSIL 偏移量到本机偏移量的映射。</span><span class="sxs-lookup"><span data-stu-id="08552-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="08552-109">没有任何返回的元素数组的排序。</span><span class="sxs-lookup"><span data-stu-id="08552-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08552-110">备注</span><span class="sxs-lookup"><span data-stu-id="08552-110">Remarks</span></span>  
 <span data-ttu-id="08552-111">`GetILToNativeMapping`方法返回有意义的结果，仅当此"icor 调试代码"实例表示了实时 (JIT) 编译的 MSIL 代码中的本机代码。</span><span class="sxs-lookup"><span data-stu-id="08552-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08552-112">惠?</span><span class="sxs-lookup"><span data-stu-id="08552-112">Requirements</span></span>  
 <span data-ttu-id="08552-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08552-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08552-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08552-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08552-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08552-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08552-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08552-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08552-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="08552-117">See Also</span></span>  
 [<span data-ttu-id="08552-118">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="08552-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
