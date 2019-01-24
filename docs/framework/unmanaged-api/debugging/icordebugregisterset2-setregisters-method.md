---
title: ICorDebugRegisterSet2::SetRegisters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f7ba8228ae47508e3aa3ac79cf635fcf4eba329
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604426"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="7e2d0-102">ICorDebugRegisterSet2::SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="7e2d0-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="7e2d0-103">`SetRegisters` 在.NET Framework 2.0 版中未实现。</span><span class="sxs-lookup"><span data-stu-id="7e2d0-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7e2d0-104">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="7e2d0-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e2d0-105">使用更高级别的操作，如[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)或[icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7e2d0-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e2d0-106">语法</span><span class="sxs-lookup"><span data-stu-id="7e2d0-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7e2d0-107">要求</span><span class="sxs-lookup"><span data-stu-id="7e2d0-107">Requirements</span></span>  
 <span data-ttu-id="7e2d0-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e2d0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e2d0-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e2d0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e2d0-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e2d0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e2d0-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e2d0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2d0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e2d0-112">See also</span></span>
- [<span data-ttu-id="7e2d0-113">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="7e2d0-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="7e2d0-114">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="7e2d0-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
