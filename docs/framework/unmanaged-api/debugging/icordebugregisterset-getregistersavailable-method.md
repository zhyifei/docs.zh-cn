---
title: "ICorDebugRegisterSet::GetRegistersAvailable 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa4dd904b07aa2c9157e61e6968e96ef797ad3f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="d5c1a-102">ICorDebugRegisterSet::GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="d5c1a-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="d5c1a-103">获取的位掩码，该值指示用于在此注册[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)当前可用。</span><span class="sxs-lookup"><span data-stu-id="d5c1a-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5c1a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5c1a-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5c1a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d5c1a-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="d5c1a-106">[out]一个位掩码，该值指示的当前可用的寄存器。</span><span class="sxs-lookup"><span data-stu-id="d5c1a-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5c1a-107">备注</span><span class="sxs-lookup"><span data-stu-id="d5c1a-107">Remarks</span></span>  
 <span data-ttu-id="d5c1a-108">如果给定的情况下无法确定其值，则寄存器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="d5c1a-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="d5c1a-109">在返回的掩码包含一位的每种寄存器 (1 << 注册索引)。</span><span class="sxs-lookup"><span data-stu-id="d5c1a-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="d5c1a-110">如果注册不可用，位值为 1 或 0 如果不可用。</span><span class="sxs-lookup"><span data-stu-id="d5c1a-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5c1a-111">要求</span><span class="sxs-lookup"><span data-stu-id="d5c1a-111">Requirements</span></span>  
 <span data-ttu-id="d5c1a-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c1a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5c1a-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5c1a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5c1a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5c1a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5c1a-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c1a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c1a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5c1a-116">See Also</span></span>  
 [<span data-ttu-id="d5c1a-117">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="d5c1a-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="d5c1a-118">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="d5c1a-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
