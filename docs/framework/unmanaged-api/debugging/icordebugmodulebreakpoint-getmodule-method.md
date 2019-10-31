---
title: ICorDebugModuleBreakpoint::GetModule 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: 6f9d8cd79ac4107817d19fc0632aeaee287d253a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097003"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="f792b-102">ICorDebugModuleBreakpoint::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="f792b-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="f792b-103">获取一个指向 "ICorDebugModule" 的接口指针，该指针引用设置此断点的模块。</span><span class="sxs-lookup"><span data-stu-id="f792b-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f792b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f792b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f792b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f792b-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="f792b-106">弄一个指针，指向用于引用设置断点的模块的 `ICorDebugModule` 接口的地址。</span><span class="sxs-lookup"><span data-stu-id="f792b-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f792b-107">要求</span><span class="sxs-lookup"><span data-stu-id="f792b-107">Requirements</span></span>  
 <span data-ttu-id="f792b-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f792b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f792b-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f792b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f792b-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f792b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f792b-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f792b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f792b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f792b-112">See also</span></span>
