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
ms.openlocfilehash: af90886390b59932d3ae146a70fc2901ec1c378d
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894672"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="c39fa-102">ICorDebugBreakpointEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="c39fa-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="c39fa-103">从当前位置开始，从枚举中获取指定数量的 ICorDebugBreakpoint 实例。</span><span class="sxs-lookup"><span data-stu-id="c39fa-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c39fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="c39fa-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c39fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="c39fa-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c39fa-106">中要检索的`ICorDebugBreakpoint`实例数。</span><span class="sxs-lookup"><span data-stu-id="c39fa-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="c39fa-107">弄指针的数组，其中每个都指向表示断点`ICorDebugBreakpoint`的对象。</span><span class="sxs-lookup"><span data-stu-id="c39fa-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c39fa-108">弄一个指针，指向实际返回`ICorDebugBreakpoint`的实例数。</span><span class="sxs-lookup"><span data-stu-id="c39fa-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="c39fa-109">如果`celt`为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="c39fa-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c39fa-110">要求</span><span class="sxs-lookup"><span data-stu-id="c39fa-110">Requirements</span></span>  
 <span data-ttu-id="c39fa-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c39fa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c39fa-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c39fa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c39fa-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c39fa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c39fa-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c39fa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
