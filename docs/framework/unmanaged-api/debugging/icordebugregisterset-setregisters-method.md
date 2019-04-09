---
title: ICorDebugRegisterSet::SetRegisters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d17c353d8e2358a1651ba3fbbb1dd718cc681f7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123785"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="4cc9f-102">ICorDebugRegisterSet::SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="4cc9f-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
`SetRegisters` <span data-ttu-id="4cc9f-103">在.NET Framework 2.0 版中未实现。</span><span class="sxs-lookup"><span data-stu-id="4cc9f-103">is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4cc9f-104">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="4cc9f-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cc9f-105">使用更高级别的操作，如[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)或[icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc9f-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc9f-106">语法</span><span class="sxs-lookup"><span data-stu-id="4cc9f-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4cc9f-107">要求</span><span class="sxs-lookup"><span data-stu-id="4cc9f-107">Requirements</span></span>  
 <span data-ttu-id="4cc9f-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc9f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc9f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cc9f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cc9f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cc9f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cc9f-111">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="4cc9f-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc9f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cc9f-112">See also</span></span>

- [<span data-ttu-id="4cc9f-113">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="4cc9f-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="4cc9f-114">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="4cc9f-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
