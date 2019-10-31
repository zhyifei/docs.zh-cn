---
title: ICorDebugBreakpoint::IsActive 方法
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
ms.openlocfilehash: 8df4e1df7836f340bb04fc47d1ca55e0fb7c9f0e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122773"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="87a48-102">ICorDebugBreakpoint::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="87a48-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="87a48-103">获取一个值，该值指示此 `ICorDebugBreakpoint` 是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="87a48-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a48-104">语法</span><span class="sxs-lookup"><span data-stu-id="87a48-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87a48-105">参数</span><span class="sxs-lookup"><span data-stu-id="87a48-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="87a48-106">[out] 如果此断点是活动的，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="87a48-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87a48-107">要求</span><span class="sxs-lookup"><span data-stu-id="87a48-107">Requirements</span></span>  
 <span data-ttu-id="87a48-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87a48-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87a48-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87a48-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87a48-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87a48-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87a48-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87a48-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
