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
ms.openlocfilehash: bd421d705a96778159cb80ad92d9ac654e88985f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414061"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="bf502-102">ICorDebugILFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="bf502-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="bf502-103">获取指令指针的值和一个描述如何获取指令指针的值的按位组合值。</span><span class="sxs-lookup"><span data-stu-id="bf502-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf502-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf502-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf502-105">参数</span><span class="sxs-lookup"><span data-stu-id="bf502-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="bf502-106">[out]指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="bf502-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="bf502-107">[out]指向 CorDebugMappingResult 枚举值，用于描述如何获取指令指针的值的按位组合的指针。</span><span class="sxs-lookup"><span data-stu-id="bf502-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf502-108">备注</span><span class="sxs-lookup"><span data-stu-id="bf502-108">Remarks</span></span>  
 <span data-ttu-id="bf502-109">指令指针的值是到函数的 Microsoft 中间语言 (MSIL) 代码的堆栈帧的偏移量。</span><span class="sxs-lookup"><span data-stu-id="bf502-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="bf502-110">如果堆栈帧处于活动状态，则此地址是要执行的下一步指令。</span><span class="sxs-lookup"><span data-stu-id="bf502-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="bf502-111">如果堆栈帧不处于活动状态，此地址是在堆栈帧重新激活时执行的下一个指令。</span><span class="sxs-lookup"><span data-stu-id="bf502-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="bf502-112">如果此帧中实时 (JIT) 编译的帧，则将通过向后将映射从实际的本机指令指针，因此该值可能只是近似确定指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="bf502-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf502-113">要求</span><span class="sxs-lookup"><span data-stu-id="bf502-113">Requirements</span></span>  
 <span data-ttu-id="bf502-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf502-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf502-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf502-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf502-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf502-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf502-117">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf502-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
