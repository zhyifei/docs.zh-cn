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
ms.openlocfilehash: d61d37448930d451b519c93909165e5e16f92765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792053"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="d15ff-102">ICorDebugRegisterSet::SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="d15ff-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="d15ff-103">.NET Framework 版本2.0 中未实现 `SetRegisters`。</span><span class="sxs-lookup"><span data-stu-id="d15ff-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d15ff-104">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="d15ff-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d15ff-105">使用较高级别的操作，如[ICorDebugILFrame：： setip](icordebugilframe-setip-method.md)或[ICorDebugNativeFrame：： setip](icordebugnativeframe-setip-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d15ff-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d15ff-106">语法</span><span class="sxs-lookup"><span data-stu-id="d15ff-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d15ff-107">需求</span><span class="sxs-lookup"><span data-stu-id="d15ff-107">Requirements</span></span>  
 <span data-ttu-id="d15ff-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d15ff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d15ff-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d15ff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d15ff-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d15ff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d15ff-111">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="d15ff-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15ff-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d15ff-112">See also</span></span>

- [<span data-ttu-id="d15ff-113">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="d15ff-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="d15ff-114">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="d15ff-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
