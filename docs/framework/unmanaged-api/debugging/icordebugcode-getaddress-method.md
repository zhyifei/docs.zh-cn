---
title: ICorDebugCode::GetAddress 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dda5883d8a1de11fa282e8b8e0fafe924f2d8b7a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494501"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="f3da1-102">ICorDebugCode::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="f3da1-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="f3da1-103">获取此"ICorDebugCode"接口表示代码段的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="f3da1-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3da1-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3da1-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3da1-105">参数</span><span class="sxs-lookup"><span data-stu-id="f3da1-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="f3da1-106">[out]一个指向代码段的 RVA。</span><span class="sxs-lookup"><span data-stu-id="f3da1-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3da1-107">要求</span><span class="sxs-lookup"><span data-stu-id="f3da1-107">Requirements</span></span>  
 <span data-ttu-id="f3da1-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3da1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3da1-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3da1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3da1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3da1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3da1-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3da1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3da1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3da1-112">See also</span></span>

