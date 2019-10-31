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
ms.openlocfilehash: d29576c6f073f1d0e8e0aea417fc38c09a8327c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122748"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="2b640-102">ICorDebugBreakpointEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="2b640-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="2b640-103">从当前位置开始，从枚举中获取指定数量的 ICorDebugBreakpoint 实例。</span><span class="sxs-lookup"><span data-stu-id="2b640-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b640-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b640-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b640-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b640-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2b640-106">中要检索的 `ICorDebugBreakpoint` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="2b640-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="2b640-107">弄指针的数组，其中每个都指向表示断点的 `ICorDebugBreakpoint` 对象。</span><span class="sxs-lookup"><span data-stu-id="2b640-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2b640-108">弄一个指针，指向实际返回的 `ICorDebugBreakpoint` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="2b640-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="2b640-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="2b640-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b640-110">要求</span><span class="sxs-lookup"><span data-stu-id="2b640-110">Requirements</span></span>  
 <span data-ttu-id="2b640-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b640-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b640-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b640-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b640-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b640-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b640-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b640-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
