---
title: "ICorDebugRegisterSet::SetRegisters 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.SetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ddf1eab6ea4689e330137fba1a676fd86ed2187
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="3e59e-102">ICorDebugRegisterSet::SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="3e59e-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="3e59e-103">`SetRegisters`在.NET Framework 2.0 版中未实现。</span><span class="sxs-lookup"><span data-stu-id="3e59e-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3e59e-104">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="3e59e-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e59e-105">使用更高级别的操作如[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)或[icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3e59e-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e59e-106">语法</span><span class="sxs-lookup"><span data-stu-id="3e59e-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3e59e-107">惠?</span><span class="sxs-lookup"><span data-stu-id="3e59e-107">Requirements</span></span>  
 <span data-ttu-id="3e59e-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e59e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e59e-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e59e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e59e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e59e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e59e-111">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="3e59e-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e59e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e59e-112">See Also</span></span>  
 [<span data-ttu-id="3e59e-113">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="3e59e-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="3e59e-114">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="3e59e-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
