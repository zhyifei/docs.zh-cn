---
title: "ICorDebugCode::GetAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 20fe5f76e36eb7f5e59f650bc813aea8ad455078
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="2e756-102">ICorDebugCode::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="2e756-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="2e756-103">此"icor 调试代码"接口表示的代码段中获取的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="2e756-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e756-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e756-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e756-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e756-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="2e756-106">[out]代码段的 RVA 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="2e756-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e756-107">惠?</span><span class="sxs-lookup"><span data-stu-id="2e756-107">Requirements</span></span>  
 <span data-ttu-id="2e756-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e756-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e756-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e756-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e756-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e756-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e756-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e756-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e756-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e756-112">See Also</span></span>  
 
