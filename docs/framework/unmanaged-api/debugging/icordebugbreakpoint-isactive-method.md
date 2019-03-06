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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5df5bed730211676acc4770c91cc6551bde0179b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57464719"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="b7e71-102">ICorDebugBreakpoint::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="b7e71-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="b7e71-103">获取一个值，该值指示是否此`ICorDebugBreakpoint`处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b7e71-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e71-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7e71-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7e71-105">参数</span><span class="sxs-lookup"><span data-stu-id="b7e71-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="b7e71-106">[out]`true`如果此断点是活动; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b7e71-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7e71-107">要求</span><span class="sxs-lookup"><span data-stu-id="b7e71-107">Requirements</span></span>  
 <span data-ttu-id="b7e71-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e71-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7e71-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7e71-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7e71-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7e71-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7e71-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7e71-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
