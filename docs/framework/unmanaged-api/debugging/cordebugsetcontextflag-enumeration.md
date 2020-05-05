---
title: CorDebugSetContextFlag 枚举
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: a3214fc4e52918716f183720c7c616b1fff74bdb
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795672"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="5250c-102">CorDebugSetContextFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="5250c-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="5250c-103">指示上下文是来自堆栈上的活动（或叶）帧，还是已通过从另一个帧展开来进行计算。</span><span class="sxs-lookup"><span data-stu-id="5250c-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5250c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5250c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="5250c-105">成员</span><span class="sxs-lookup"><span data-stu-id="5250c-105">Members</span></span>  
  
|<span data-ttu-id="5250c-106">成员</span><span class="sxs-lookup"><span data-stu-id="5250c-106">Member</span></span>|<span data-ttu-id="5250c-107">说明</span><span class="sxs-lookup"><span data-stu-id="5250c-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5250c-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="5250c-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="5250c-109">上下文是线程的活动上下文。</span><span class="sxs-lookup"><span data-stu-id="5250c-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="5250c-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="5250c-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="5250c-111">已通过从另一个帧展开上下文来计算上下文。</span><span class="sxs-lookup"><span data-stu-id="5250c-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5250c-112">备注</span><span class="sxs-lookup"><span data-stu-id="5250c-112">Remarks</span></span>  
 <span data-ttu-id="5250c-113">`CorDebugSetContextFlag`提供[ICorDebugStackWalk：： SetContext](icordebugstackwalk-setcontext-method.md)方法使用的值。</span><span class="sxs-lookup"><span data-stu-id="5250c-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5250c-114">要求</span><span class="sxs-lookup"><span data-stu-id="5250c-114">Requirements</span></span>  
 <span data-ttu-id="5250c-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5250c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5250c-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5250c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5250c-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5250c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5250c-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5250c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5250c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5250c-119">See also</span></span>

- [<span data-ttu-id="5250c-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="5250c-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="5250c-121">调试</span><span class="sxs-lookup"><span data-stu-id="5250c-121">Debugging</span></span>](index.md)
