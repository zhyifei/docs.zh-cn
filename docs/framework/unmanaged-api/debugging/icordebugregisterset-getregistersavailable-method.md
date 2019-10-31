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
ms.openlocfilehash: 9d8bd6ab13fa408fd7390aaeb76baee274742f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137693"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="ffafb-102">ICorDebugRegisterSet::GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="ffafb-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="ffafb-103">获取指示此[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)中的哪些寄存器当前可用的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ffafb-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffafb-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffafb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffafb-105">参数</span><span class="sxs-lookup"><span data-stu-id="ffafb-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="ffafb-106">弄一个位掩码，用于指示当前可用的注册。</span><span class="sxs-lookup"><span data-stu-id="ffafb-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffafb-107">备注</span><span class="sxs-lookup"><span data-stu-id="ffafb-107">Remarks</span></span>  
 <span data-ttu-id="ffafb-108">如果无法为给定情况确定其值，则寄存器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="ffafb-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="ffafb-109">返回的掩码对每个寄存器都包含一个位（1 < < 注册索引）。</span><span class="sxs-lookup"><span data-stu-id="ffafb-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="ffafb-110">如果寄存器可用，则位值为 1; 否则为0。</span><span class="sxs-lookup"><span data-stu-id="ffafb-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffafb-111">要求</span><span class="sxs-lookup"><span data-stu-id="ffafb-111">Requirements</span></span>  
 <span data-ttu-id="ffafb-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffafb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffafb-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffafb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffafb-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffafb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffafb-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffafb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffafb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffafb-116">See also</span></span>

- [<span data-ttu-id="ffafb-117">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="ffafb-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="ffafb-118">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="ffafb-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
