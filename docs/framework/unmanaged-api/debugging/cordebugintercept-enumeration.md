---
title: CorDebugIntercept 枚举
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 18a5e337b6026a20a95b1c29f3d7bda5187efc66
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795854"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="69169-102">CorDebugIntercept 枚举</span><span class="sxs-lookup"><span data-stu-id="69169-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="69169-103">指示可截获（即可单步执行）的代码的类型。</span><span class="sxs-lookup"><span data-stu-id="69169-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69169-104">语法</span><span class="sxs-lookup"><span data-stu-id="69169-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="69169-105">成员</span><span class="sxs-lookup"><span data-stu-id="69169-105">Members</span></span>  
  
|<span data-ttu-id="69169-106">成员</span><span class="sxs-lookup"><span data-stu-id="69169-106">Member</span></span>|<span data-ttu-id="69169-107">说明</span><span class="sxs-lookup"><span data-stu-id="69169-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="69169-108">未截获任何代码。</span><span class="sxs-lookup"><span data-stu-id="69169-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="69169-109">可以截获构造函数。</span><span class="sxs-lookup"><span data-stu-id="69169-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="69169-110">可以截获异常筛选器。</span><span class="sxs-lookup"><span data-stu-id="69169-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="69169-111">可以截获强制保护的代码。</span><span class="sxs-lookup"><span data-stu-id="69169-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="69169-112">可以截获上下文策略。</span><span class="sxs-lookup"><span data-stu-id="69169-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="69169-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="69169-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="69169-114">可以截获所有代码。</span><span class="sxs-lookup"><span data-stu-id="69169-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69169-115">备注</span><span class="sxs-lookup"><span data-stu-id="69169-115">Remarks</span></span>  
 <span data-ttu-id="69169-116">使用[ICorDebugStepper：： SetInterceptMask](icordebugstepper-setinterceptmask-method.md)方法来建立可以截获的代码类型。</span><span class="sxs-lookup"><span data-stu-id="69169-116">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69169-117">要求</span><span class="sxs-lookup"><span data-stu-id="69169-117">Requirements</span></span>  
 <span data-ttu-id="69169-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69169-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69169-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69169-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69169-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69169-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69169-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69169-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69169-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69169-122">See also</span></span>

- [<span data-ttu-id="69169-123">调试枚举</span><span class="sxs-lookup"><span data-stu-id="69169-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
