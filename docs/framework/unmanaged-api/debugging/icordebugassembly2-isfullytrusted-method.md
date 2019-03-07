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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd3b977a894f8cb1fc9a866f5a43265d917db513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494436"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="28f92-102">ICorDebugAssembly2::IsFullyTrusted 方法</span><span class="sxs-lookup"><span data-stu-id="28f92-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="28f92-103">获取一个值，该值指示运行时安全系统是否已向程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="28f92-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f92-104">语法</span><span class="sxs-lookup"><span data-stu-id="28f92-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28f92-105">参数</span><span class="sxs-lookup"><span data-stu-id="28f92-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="28f92-106">[out]`true`程序集是否已被授予完全信任，由运行时安全系统中; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="28f92-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28f92-107">备注</span><span class="sxs-lookup"><span data-stu-id="28f92-107">Remarks</span></span>  
 <span data-ttu-id="28f92-108">此方法返回 HRESULT 的 CORDBG_E_NOTREADY 如果程序集的安全策略不尚未已解决，也就是说，如果没有在程序集中的代码具有尚未运行。</span><span class="sxs-lookup"><span data-stu-id="28f92-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f92-109">要求</span><span class="sxs-lookup"><span data-stu-id="28f92-109">Requirements</span></span>  
 <span data-ttu-id="28f92-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28f92-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28f92-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28f92-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28f92-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28f92-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28f92-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28f92-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
