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
ms.openlocfilehash: 2dce97db3d209c51270a51ae92e9dce0b6861998
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791999"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="c2d98-102">ICorDebugRegisterSet2::SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="c2d98-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="c2d98-103">.NET Framework 版本2.0 中未实现 `SetRegisters`。</span><span class="sxs-lookup"><span data-stu-id="c2d98-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="c2d98-104">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c2d98-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2d98-105">使用较高级别的操作，如[ICorDebugILFrame：： setip](icordebugilframe-setip-method.md)或[ICorDebugNativeFrame：： setip](icordebugnativeframe-setip-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d98-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d98-106">语法</span><span class="sxs-lookup"><span data-stu-id="c2d98-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c2d98-107">需求</span><span class="sxs-lookup"><span data-stu-id="c2d98-107">Requirements</span></span>  
 <span data-ttu-id="c2d98-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d98-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d98-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2d98-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2d98-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2d98-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2d98-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d98-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d98-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2d98-112">See also</span></span>

- [<span data-ttu-id="c2d98-113">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="c2d98-113">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="c2d98-114">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="c2d98-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
