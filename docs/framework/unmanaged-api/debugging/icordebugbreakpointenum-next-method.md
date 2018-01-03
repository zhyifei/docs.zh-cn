---
title: "ICorDebugBreakpointEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpointEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b81da25a630b034d4ec2f277f738a5337bdbec3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="03751-102">ICorDebugBreakpointEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="03751-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="03751-103">获取指定的数量的 ICorDebugBreakpoint 实例的枚举，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="03751-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03751-104">语法</span><span class="sxs-lookup"><span data-stu-id="03751-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03751-105">参数</span><span class="sxs-lookup"><span data-stu-id="03751-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="03751-106">[in]数`ICorDebugBreakpoint`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="03751-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="03751-107">[out]一个指针，其中每个指向数组`ICorDebugBreakpoint`表示一个断点的对象。</span><span class="sxs-lookup"><span data-stu-id="03751-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="03751-108">[out]指向数`ICorDebugBreakpoint`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="03751-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="03751-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="03751-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03751-110">惠?</span><span class="sxs-lookup"><span data-stu-id="03751-110">Requirements</span></span>  
 <span data-ttu-id="03751-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="03751-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03751-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03751-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03751-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03751-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03751-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03751-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
