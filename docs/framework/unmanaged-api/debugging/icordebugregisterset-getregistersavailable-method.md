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
ms.openlocfilehash: 74eef0c1ec456d647e5a58e5009d2c77e5002289
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378293"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="91e6e-102">ICorDebugRegisterSet::GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="91e6e-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="91e6e-103">获取指示此[ICorDebugRegisterSet](icordebugregisterset-interface.md)中的哪些寄存器当前可用的位掩码。</span><span class="sxs-lookup"><span data-stu-id="91e6e-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91e6e-104">语法</span><span class="sxs-lookup"><span data-stu-id="91e6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91e6e-105">参数</span><span class="sxs-lookup"><span data-stu-id="91e6e-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="91e6e-106">弄一个位掩码，用于指示当前可用的注册。</span><span class="sxs-lookup"><span data-stu-id="91e6e-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91e6e-107">备注</span><span class="sxs-lookup"><span data-stu-id="91e6e-107">Remarks</span></span>  
 <span data-ttu-id="91e6e-108">如果无法为给定情况确定其值，则寄存器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="91e6e-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="91e6e-109">返回的掩码对每个寄存器都包含一个位（1 << 注册索引）。</span><span class="sxs-lookup"><span data-stu-id="91e6e-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="91e6e-110">如果寄存器可用，则位值为 1; 否则为0。</span><span class="sxs-lookup"><span data-stu-id="91e6e-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91e6e-111">要求</span><span class="sxs-lookup"><span data-stu-id="91e6e-111">Requirements</span></span>  
 <span data-ttu-id="91e6e-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91e6e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91e6e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91e6e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91e6e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91e6e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91e6e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91e6e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e6e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="91e6e-116">See also</span></span>

- [<span data-ttu-id="91e6e-117">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="91e6e-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="91e6e-118">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="91e6e-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
