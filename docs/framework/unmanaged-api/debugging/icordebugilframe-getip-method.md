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
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178826"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="ee995-102">ICorDebugILFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="ee995-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="ee995-103">获取指令指针的值和描述指令指针值的位组合值。</span><span class="sxs-lookup"><span data-stu-id="ee995-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee995-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee995-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee995-105">parameters</span><span class="sxs-lookup"><span data-stu-id="ee995-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="ee995-106">[出]指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="ee995-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="ee995-107">[出]指向 CorDebugMappingResult 枚举值的位状组合的指针，用于描述如何获取指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="ee995-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee995-108">备注</span><span class="sxs-lookup"><span data-stu-id="ee995-108">Remarks</span></span>  
 <span data-ttu-id="ee995-109">指令指针的值是堆栈帧的偏移量到函数的 Microsoft 中间语言 （MSIL） 代码中。</span><span class="sxs-lookup"><span data-stu-id="ee995-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="ee995-110">如果堆栈帧处于活动状态，则此地址是执行的下一个指令。</span><span class="sxs-lookup"><span data-stu-id="ee995-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="ee995-111">如果堆栈帧未处于活动状态，则此地址是重新激活堆栈帧时执行的下一个指令。</span><span class="sxs-lookup"><span data-stu-id="ee995-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="ee995-112">如果此帧是实时 （JIT） 编译帧，则指令指针的值将通过从实际本机指令指针向后映射来确定，因此该值可能仅是近似值。</span><span class="sxs-lookup"><span data-stu-id="ee995-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee995-113">要求</span><span class="sxs-lookup"><span data-stu-id="ee995-113">Requirements</span></span>  
 <span data-ttu-id="ee995-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee995-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee995-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee995-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee995-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee995-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee995-117">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee995-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
