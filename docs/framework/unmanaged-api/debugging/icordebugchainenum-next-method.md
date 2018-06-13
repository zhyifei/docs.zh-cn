---
title: ICorDebugChainEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd4f27b958aa4b25c2662d8a5e9da6bcdc73d5d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404451"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="41970-102">ICorDebugChainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="41970-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="41970-103">获取指定的数量的 ICorDebugChain 实例的枚举，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="41970-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41970-104">语法</span><span class="sxs-lookup"><span data-stu-id="41970-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41970-105">参数</span><span class="sxs-lookup"><span data-stu-id="41970-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="41970-106">[in]数`ICorDebugChain`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="41970-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="41970-107">[out]一个指针，其中每个指向数组`ICorDebugChain`表示链的对象。</span><span class="sxs-lookup"><span data-stu-id="41970-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="41970-108">[out]指向数`ICorDebugChain`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="41970-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="41970-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="41970-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41970-110">要求</span><span class="sxs-lookup"><span data-stu-id="41970-110">Requirements</span></span>  
 <span data-ttu-id="41970-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41970-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41970-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41970-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41970-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41970-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41970-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41970-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
