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
ms.openlocfilehash: f341098268f735a576bdbc5f0cea52f1a7e14f90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156034"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="a05f6-102">ICorDebugRegisterSet::GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="a05f6-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="a05f6-103">获取的位掩码，指示用于在此注册[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)当前可用。</span><span class="sxs-lookup"><span data-stu-id="a05f6-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a05f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="a05f6-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a05f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="a05f6-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="a05f6-106">[out]一个位掩码，指示的当前可用的寄存器。</span><span class="sxs-lookup"><span data-stu-id="a05f6-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a05f6-107">备注</span><span class="sxs-lookup"><span data-stu-id="a05f6-107">Remarks</span></span>  
 <span data-ttu-id="a05f6-108">一个函数注册表，可能不能为给定的情况下确定其值的情况下不可用。</span><span class="sxs-lookup"><span data-stu-id="a05f6-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="a05f6-109">返回的掩码包含的每个注册的一位 (1 << 注册索引)。</span><span class="sxs-lookup"><span data-stu-id="a05f6-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="a05f6-110">如果注册不可用，位值为 1 或 0，如果不可用。</span><span class="sxs-lookup"><span data-stu-id="a05f6-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a05f6-111">要求</span><span class="sxs-lookup"><span data-stu-id="a05f6-111">Requirements</span></span>  
 <span data-ttu-id="a05f6-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a05f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a05f6-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a05f6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a05f6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a05f6-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a05f6-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a05f6-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a05f6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a05f6-116">See also</span></span>

- [<span data-ttu-id="a05f6-117">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="a05f6-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="a05f6-118">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="a05f6-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
