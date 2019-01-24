---
title: StackTrace_SimpleContext 结构
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 510ef77f217cdd6e3441e3d6684d431fc31307fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698916"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="063c0-102">StackTrace_SimpleContext 结构</span><span class="sxs-lookup"><span data-stu-id="063c0-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="063c0-103">提供可用于代替完整的 `CONTEXT` 结构的简单上下文。</span><span class="sxs-lookup"><span data-stu-id="063c0-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="063c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="063c0-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="063c0-105">成员</span><span class="sxs-lookup"><span data-stu-id="063c0-105">Members</span></span>  
  
|<span data-ttu-id="063c0-106">成员</span><span class="sxs-lookup"><span data-stu-id="063c0-106">Member</span></span>|<span data-ttu-id="063c0-107">描述</span><span class="sxs-lookup"><span data-stu-id="063c0-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="063c0-108">堆栈指针或在 x86 上的 enter 堆栈指针 (ESP) 平台。</span><span class="sxs-lookup"><span data-stu-id="063c0-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="063c0-109">帧偏移量或在 x86 上的 EBP 寄存器平台。</span><span class="sxs-lookup"><span data-stu-id="063c0-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="063c0-110">指令指针或在 x86 上的输入指令指针 (EIP) 平台。</span><span class="sxs-lookup"><span data-stu-id="063c0-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="063c0-111">备注</span><span class="sxs-lookup"><span data-stu-id="063c0-111">Remarks</span></span>  
 <span data-ttu-id="063c0-112">由于堆栈跟踪函数通常需要返回地址、 帧偏移量和堆栈地址，因此你可以选择使用`SimpleContext`而不是一个较大的结构`CONTEXT`结构。</span><span class="sxs-lookup"><span data-stu-id="063c0-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="063c0-113">要求</span><span class="sxs-lookup"><span data-stu-id="063c0-113">Requirements</span></span>  
 <span data-ttu-id="063c0-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="063c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="063c0-115">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="063c0-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="063c0-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="063c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063c0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="063c0-117">See also</span></span>
- [<span data-ttu-id="063c0-118">调试结构</span><span class="sxs-lookup"><span data-stu-id="063c0-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="063c0-119">调试</span><span class="sxs-lookup"><span data-stu-id="063c0-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
