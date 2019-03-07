---
title: ICorDebugBreakpointEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18b65eb3e733fa7970e4c0e7de09755598eaf149
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474977"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="6758d-102">ICorDebugBreakpointEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="6758d-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="6758d-103">从当前位置开始枚举中获取指定的数量的 ICorDebugBreakpoint 实例。</span><span class="sxs-lookup"><span data-stu-id="6758d-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6758d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6758d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6758d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6758d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6758d-106">[in]数`ICorDebugBreakpoint`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="6758d-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="6758d-107">[out]一个指针，其中每个指向数组`ICorDebugBreakpoint`表示断点的对象。</span><span class="sxs-lookup"><span data-stu-id="6758d-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6758d-108">[out]指向数`ICorDebugBreakpoint`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="6758d-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="6758d-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="6758d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6758d-110">要求</span><span class="sxs-lookup"><span data-stu-id="6758d-110">Requirements</span></span>  
 <span data-ttu-id="6758d-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6758d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6758d-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6758d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6758d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6758d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6758d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6758d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
