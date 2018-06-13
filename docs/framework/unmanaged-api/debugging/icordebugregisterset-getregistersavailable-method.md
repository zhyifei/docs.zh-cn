---
title: ICorDebugRegisterSet::GetRegistersAvailable 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3174be7237bcdbd5a12f38f04d6e67d9eb9a573e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421848"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="453f2-102">ICorDebugRegisterSet::GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="453f2-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="453f2-103">获取的位掩码，该值指示用于在此注册[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)当前可用。</span><span class="sxs-lookup"><span data-stu-id="453f2-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="453f2-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="453f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="453f2-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="453f2-106">[out]一个位掩码，该值指示的当前可用的寄存器。</span><span class="sxs-lookup"><span data-stu-id="453f2-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="453f2-107">备注</span><span class="sxs-lookup"><span data-stu-id="453f2-107">Remarks</span></span>  
 <span data-ttu-id="453f2-108">如果给定的情况下无法确定其值，则寄存器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="453f2-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="453f2-109">在返回的掩码包含一位的每种寄存器 (1 << 注册索引)。</span><span class="sxs-lookup"><span data-stu-id="453f2-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="453f2-110">如果注册不可用，位值为 1 或 0 如果不可用。</span><span class="sxs-lookup"><span data-stu-id="453f2-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="453f2-111">要求</span><span class="sxs-lookup"><span data-stu-id="453f2-111">Requirements</span></span>  
 <span data-ttu-id="453f2-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="453f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453f2-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="453f2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="453f2-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="453f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="453f2-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453f2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="453f2-116">See Also</span></span>  
 [<span data-ttu-id="453f2-117">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="453f2-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="453f2-118">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="453f2-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
