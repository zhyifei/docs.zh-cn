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
ms.openlocfilehash: 229bf968d21516d48468610c8f47367324fb6b13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695512"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="ce3e1-102">ICorDebugCode::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="ce3e1-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="ce3e1-103">获取此"ICorDebugCode"接口表示代码段的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="ce3e1-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce3e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce3e1-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce3e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce3e1-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="ce3e1-106">[out]一个指向代码段的 RVA。</span><span class="sxs-lookup"><span data-stu-id="ce3e1-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce3e1-107">要求</span><span class="sxs-lookup"><span data-stu-id="ce3e1-107">Requirements</span></span>  
 <span data-ttu-id="ce3e1-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce3e1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce3e1-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce3e1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce3e1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce3e1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce3e1-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce3e1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3e1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce3e1-112">See also</span></span>

