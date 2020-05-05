---
title: CorDebugExceptionObjectStackFrame 结构
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795919"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="00693-102">CorDebugExceptionObjectStackFrame 结构</span><span class="sxs-lookup"><span data-stu-id="00693-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="00693-103">表示异常对象中的堆栈帧信息。</span><span class="sxs-lookup"><span data-stu-id="00693-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00693-104">语法</span><span class="sxs-lookup"><span data-stu-id="00693-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="00693-105">成员</span><span class="sxs-lookup"><span data-stu-id="00693-105">Members</span></span>  
  
|<span data-ttu-id="00693-106">成员</span><span class="sxs-lookup"><span data-stu-id="00693-106">Member</span></span>|<span data-ttu-id="00693-107">说明</span><span class="sxs-lookup"><span data-stu-id="00693-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="00693-108">指向当前帧的 ICorDebugModule 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="00693-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="00693-109">当前帧的指令指针（EIP/裂缝）的值。</span><span class="sxs-lookup"><span data-stu-id="00693-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="00693-110">当前帧的方法标记。</span><span class="sxs-lookup"><span data-stu-id="00693-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="00693-111">一个值，该值指示帧是否为外部异常中的最后一个帧。</span><span class="sxs-lookup"><span data-stu-id="00693-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00693-112">备注</span><span class="sxs-lookup"><span data-stu-id="00693-112">Remarks</span></span>  
 <span data-ttu-id="00693-113">当不再使用 ICorDebugModule 对象时，调用方必须释放指向该对象的指针。</span><span class="sxs-lookup"><span data-stu-id="00693-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00693-114">要求</span><span class="sxs-lookup"><span data-stu-id="00693-114">Requirements</span></span>  
 <span data-ttu-id="00693-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00693-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00693-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00693-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00693-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00693-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00693-118">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00693-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00693-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00693-119">See also</span></span>

- [<span data-ttu-id="00693-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="00693-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="00693-121">调试</span><span class="sxs-lookup"><span data-stu-id="00693-121">Debugging</span></span>](index.md)
