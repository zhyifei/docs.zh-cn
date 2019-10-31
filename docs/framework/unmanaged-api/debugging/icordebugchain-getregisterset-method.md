---
title: ICorDebugChain::GetRegisterSet 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: d6ee36ac4d4510637e5f8240c3b8930a9bec7970
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123834"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="44109-102">ICorDebugChain::GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="44109-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="44109-103">获取此链的活动部分的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="44109-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44109-104">语法</span><span class="sxs-lookup"><span data-stu-id="44109-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44109-105">参数</span><span class="sxs-lookup"><span data-stu-id="44109-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="44109-106">弄指向[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)对象的地址的指针，该对象表示此链的活动部分的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="44109-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44109-107">要求</span><span class="sxs-lookup"><span data-stu-id="44109-107">Requirements</span></span>  
 <span data-ttu-id="44109-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44109-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44109-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44109-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44109-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44109-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44109-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44109-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
