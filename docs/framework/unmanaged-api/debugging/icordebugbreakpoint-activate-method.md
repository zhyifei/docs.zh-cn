---
title: ICorDebugBreakpoint::Activate 方法
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
ms.openlocfilehash: 50794e96484432c8b7c203f6b8caa60130068a8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122795"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="9332e-102">ICorDebugBreakpoint::Activate 方法</span><span class="sxs-lookup"><span data-stu-id="9332e-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="9332e-103">设置此 `ICorDebugBreakpoint`的活动状态。</span><span class="sxs-lookup"><span data-stu-id="9332e-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9332e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9332e-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9332e-105">参数</span><span class="sxs-lookup"><span data-stu-id="9332e-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="9332e-106">中将此值设置为 "`true`" 以将状态指定为 "活动";否则，请将此值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="9332e-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9332e-107">要求</span><span class="sxs-lookup"><span data-stu-id="9332e-107">Requirements</span></span>  
 <span data-ttu-id="9332e-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9332e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9332e-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9332e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9332e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9332e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9332e-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9332e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
