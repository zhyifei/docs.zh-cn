---
title: "ICorDebugILFrame::CanSetIP 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22d0df9add0a4ce35b1a590d65e30a6756fec49c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="f25bb-102">ICorDebugILFrame::CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="f25bb-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="f25bb-103">获取一个 HRESULT，指示它是否可以安全地将指令指针设置为 Microsoft 中间语言 (MSIL) 代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="f25bb-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f25bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="f25bb-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f25bb-105">参数</span><span class="sxs-lookup"><span data-stu-id="f25bb-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f25bb-106">[in]指令指针所需的设置。</span><span class="sxs-lookup"><span data-stu-id="f25bb-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f25bb-107">备注</span><span class="sxs-lookup"><span data-stu-id="f25bb-107">Remarks</span></span>  
 <span data-ttu-id="f25bb-108">使用`CanSetIP`方法之前调用[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f25bb-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="f25bb-109">如果`CanSetIP`返回任何 HRESULT 以外，则为 S_OK，仍可以调用`ICorDebugILFrame::SetIP`，但不能保证，调试器将继续正在调试的代码的安全并正确地执行。</span><span class="sxs-lookup"><span data-stu-id="f25bb-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f25bb-110">惠?</span><span class="sxs-lookup"><span data-stu-id="f25bb-110">Requirements</span></span>  
 <span data-ttu-id="f25bb-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f25bb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f25bb-112">**标头：** CorDebug.idl，CorDebug，h</span><span class="sxs-lookup"><span data-stu-id="f25bb-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="f25bb-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f25bb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f25bb-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f25bb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
