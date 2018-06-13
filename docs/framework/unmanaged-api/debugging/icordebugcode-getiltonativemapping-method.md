---
title: ICorDebugCode::GetILToNativeMapping 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13ec60999db88b9d7191a3866fcebe8098b4edee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411381"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="85a0e-102">ICorDebugCode::GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="85a0e-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="85a0e-103">获取表示 microsoft 中间语言 (MSIL) 偏移量到本机偏移量的映射的"COR_DEBUG_IL_TO_NATIVE_MAP"实例的数组。</span><span class="sxs-lookup"><span data-stu-id="85a0e-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="85a0e-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85a0e-105">参数</span><span class="sxs-lookup"><span data-stu-id="85a0e-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="85a0e-106">[in] `map` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="85a0e-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="85a0e-107">[out]指向元素中返回的实际数目`map`数组。</span><span class="sxs-lookup"><span data-stu-id="85a0e-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="85a0e-108">[out]数组`COR_DEBUG_IL_TO_NATIVE_MAP`结构，其中每个表示从 MSIL 偏移量到本机偏移量的映射。</span><span class="sxs-lookup"><span data-stu-id="85a0e-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="85a0e-109">没有任何返回的元素数组的排序。</span><span class="sxs-lookup"><span data-stu-id="85a0e-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85a0e-110">备注</span><span class="sxs-lookup"><span data-stu-id="85a0e-110">Remarks</span></span>  
 <span data-ttu-id="85a0e-111">`GetILToNativeMapping`方法返回有意义的结果，仅当此"icor 调试代码"实例表示了实时 (JIT) 编译的 MSIL 代码中的本机代码。</span><span class="sxs-lookup"><span data-stu-id="85a0e-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85a0e-112">要求</span><span class="sxs-lookup"><span data-stu-id="85a0e-112">Requirements</span></span>  
 <span data-ttu-id="85a0e-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85a0e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85a0e-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85a0e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85a0e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85a0e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85a0e-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85a0e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a0e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="85a0e-117">See Also</span></span>  
 [<span data-ttu-id="85a0e-118">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="85a0e-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
