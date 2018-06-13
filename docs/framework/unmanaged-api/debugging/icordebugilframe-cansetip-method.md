---
title: ICorDebugILFrame::CanSetIP 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad1ea4da252fe9fac89faa79195b6a6de245ad9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414695"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="89b6a-102">ICorDebugILFrame::CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="89b6a-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="89b6a-103">获取一个 HRESULT，指示它是否可以安全地将指令指针设置为 Microsoft 中间语言 (MSIL) 代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="89b6a-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b6a-104">语法</span><span class="sxs-lookup"><span data-stu-id="89b6a-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89b6a-105">参数</span><span class="sxs-lookup"><span data-stu-id="89b6a-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="89b6a-106">[in]指令指针所需的设置。</span><span class="sxs-lookup"><span data-stu-id="89b6a-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89b6a-107">备注</span><span class="sxs-lookup"><span data-stu-id="89b6a-107">Remarks</span></span>  
 <span data-ttu-id="89b6a-108">使用`CanSetIP`方法之前调用[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="89b6a-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="89b6a-109">如果`CanSetIP`返回任何 HRESULT 以外，则为 S_OK，仍可以调用`ICorDebugILFrame::SetIP`，但不能保证，调试器将继续正在调试的代码的安全并正确地执行。</span><span class="sxs-lookup"><span data-stu-id="89b6a-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89b6a-110">要求</span><span class="sxs-lookup"><span data-stu-id="89b6a-110">Requirements</span></span>  
 <span data-ttu-id="89b6a-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89b6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89b6a-112">**标头：** CorDebug.idl，CorDebug，h</span><span class="sxs-lookup"><span data-stu-id="89b6a-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="89b6a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89b6a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89b6a-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89b6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
