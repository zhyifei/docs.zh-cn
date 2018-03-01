---
title: "StackTrace_SimpleContext 结构"
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
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 756c1d4129aebedea46443613d286a51562a3896
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="a112a-102">StackTrace_SimpleContext 结构</span><span class="sxs-lookup"><span data-stu-id="a112a-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="a112a-103">提供可用于代替完整的 `CONTEXT` 结构的简单上下文。</span><span class="sxs-lookup"><span data-stu-id="a112a-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a112a-104">语法</span><span class="sxs-lookup"><span data-stu-id="a112a-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="a112a-105">成员</span><span class="sxs-lookup"><span data-stu-id="a112a-105">Members</span></span>  
  
|<span data-ttu-id="a112a-106">成员</span><span class="sxs-lookup"><span data-stu-id="a112a-106">Member</span></span>|<span data-ttu-id="a112a-107">描述</span><span class="sxs-lookup"><span data-stu-id="a112a-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="a112a-108">堆栈指针或在 x86 上的输入堆栈指针 (ESP) 平台。</span><span class="sxs-lookup"><span data-stu-id="a112a-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="a112a-109">帧偏移量或在 x86 上的 EBP 寄存器平台。</span><span class="sxs-lookup"><span data-stu-id="a112a-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="a112a-110">指令指针或输入指令指针 (EIP) 在 x86 平台。</span><span class="sxs-lookup"><span data-stu-id="a112a-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a112a-111">备注</span><span class="sxs-lookup"><span data-stu-id="a112a-111">Remarks</span></span>  
 <span data-ttu-id="a112a-112">因为堆栈跟踪函数通常需要返回地址、 帧偏移量和堆栈地址，你可以选择使用`SimpleContext`而不是较大的结构`CONTEXT`结构。</span><span class="sxs-lookup"><span data-stu-id="a112a-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a112a-113">惠?</span><span class="sxs-lookup"><span data-stu-id="a112a-113">Requirements</span></span>  
 <span data-ttu-id="a112a-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a112a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a112a-115">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="a112a-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="a112a-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a112a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a112a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a112a-117">See Also</span></span>  
 [<span data-ttu-id="a112a-118">调试结构</span><span class="sxs-lookup"><span data-stu-id="a112a-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="a112a-119">调试</span><span class="sxs-lookup"><span data-stu-id="a112a-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
