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
ms.openlocfilehash: 26df40297d080d1ccc9464f7b09e7731f135e270
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489821"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="8af81-102">ICorDebugChainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="8af81-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="8af81-103">从当前位置开始枚举中获取指定的数量的 ICorDebugChain 实例。</span><span class="sxs-lookup"><span data-stu-id="8af81-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af81-104">语法</span><span class="sxs-lookup"><span data-stu-id="8af81-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8af81-105">参数</span><span class="sxs-lookup"><span data-stu-id="8af81-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8af81-106">[in]数`ICorDebugChain`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="8af81-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="8af81-107">[out]一个指针，其中每个指向数组`ICorDebugChain`对象，表示链。</span><span class="sxs-lookup"><span data-stu-id="8af81-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8af81-108">[out]指向数`ICorDebugChain`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="8af81-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="8af81-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="8af81-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af81-110">要求</span><span class="sxs-lookup"><span data-stu-id="8af81-110">Requirements</span></span>  
 <span data-ttu-id="8af81-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8af81-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af81-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8af81-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8af81-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8af81-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8af81-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af81-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
