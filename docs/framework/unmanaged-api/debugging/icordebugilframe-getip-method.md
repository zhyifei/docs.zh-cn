---
title: ICorDebugILFrame::GetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a7b8985e7580282d0e38205f9b1d6078f86cee6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988606"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="cdc3e-102">ICorDebugILFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="cdc3e-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="cdc3e-103">获取指令指针的值和一个说明如何获取指令指针的值的按位组合值。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc3e-104">语法</span><span class="sxs-lookup"><span data-stu-id="cdc3e-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdc3e-105">参数</span><span class="sxs-lookup"><span data-stu-id="cdc3e-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="cdc3e-106">[out]指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="cdc3e-107">[out]指向介绍如何获取指令指针的值的 CorDebugMappingResult 枚举值的按位组合的指针。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdc3e-108">备注</span><span class="sxs-lookup"><span data-stu-id="cdc3e-108">Remarks</span></span>  
 <span data-ttu-id="cdc3e-109">指令指针的值是函数的 Microsoft 中间语言 (MSIL) 代码中的堆栈帧的偏移量位置。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="cdc3e-110">如果堆栈帧处于活动状态，此地址将是下一步要执行的指令。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="cdc3e-111">如果堆栈帧未处于活动状态，此地址是执行堆栈帧重新激活时的下一个指令。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="cdc3e-112">如果此帧中实时 (JIT) 编译的帧，指令指针的值将确定通过向后将映射从实际的本机指令指针，因此该值可能只是近似。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdc3e-113">要求</span><span class="sxs-lookup"><span data-stu-id="cdc3e-113">Requirements</span></span>  
 <span data-ttu-id="cdc3e-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc3e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdc3e-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdc3e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdc3e-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdc3e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdc3e-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdc3e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
