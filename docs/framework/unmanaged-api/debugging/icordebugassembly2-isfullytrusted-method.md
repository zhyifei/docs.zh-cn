---
title: ICorDebugAssembly2::IsFullyTrusted 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133955"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="e2d88-102">ICorDebugAssembly2::IsFullyTrusted 方法</span><span class="sxs-lookup"><span data-stu-id="e2d88-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="e2d88-103">获取一个值，该值指示运行时安全系统是否已向程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="e2d88-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d88-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2d88-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2d88-105">参数</span><span class="sxs-lookup"><span data-stu-id="e2d88-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="e2d88-106">[out] 如果运行时安全系统已向程序集授予完全信任，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="e2d88-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2d88-107">备注</span><span class="sxs-lookup"><span data-stu-id="e2d88-107">Remarks</span></span>  
 <span data-ttu-id="e2d88-108">如果程序集的安全策略尚未解析（即，如果尚未运行程序集中的代码），则此方法将返回 CORDBG_E_NOTREADY 的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="e2d88-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d88-109">要求</span><span class="sxs-lookup"><span data-stu-id="e2d88-109">Requirements</span></span>  
 <span data-ttu-id="e2d88-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2d88-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d88-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2d88-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2d88-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d88-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2d88-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d88-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
