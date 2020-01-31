---
title: CorDebugExceptionFlags 枚举
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: 6ef81e224f3573021ee96ac313ec4923928dedad
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789403"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="c55ac-102">CorDebugExceptionFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="c55ac-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="c55ac-103">提供有关异常的附加信息。</span><span class="sxs-lookup"><span data-stu-id="c55ac-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="c55ac-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c55ac-105">Members</span><span class="sxs-lookup"><span data-stu-id="c55ac-105">Members</span></span>  
  
|<span data-ttu-id="c55ac-106">成员</span><span class="sxs-lookup"><span data-stu-id="c55ac-106">Member</span></span>|<span data-ttu-id="c55ac-107">描述</span><span class="sxs-lookup"><span data-stu-id="c55ac-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="c55ac-108">没有异常。</span><span class="sxs-lookup"><span data-stu-id="c55ac-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="c55ac-109">异常是可截获的。</span><span class="sxs-lookup"><span data-stu-id="c55ac-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="c55ac-110">异常的发生时间可能仍然会使调试器无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="c55ac-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="c55ac-111">例如，如果当前回调或实时 (JIT) 连接引起的异常事件下没有托管代码，则无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="c55ac-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c55ac-112">备注</span><span class="sxs-lookup"><span data-stu-id="c55ac-112">Remarks</span></span>  
 <span data-ttu-id="c55ac-113">以后的版本可能会向此枚举中添加新值，因此你应针对意外值准备使用 `CorDebugExceptionFlags` 的代码。</span><span class="sxs-lookup"><span data-stu-id="c55ac-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c55ac-114">需求</span><span class="sxs-lookup"><span data-stu-id="c55ac-114">Requirements</span></span>  
 <span data-ttu-id="c55ac-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c55ac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c55ac-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c55ac-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c55ac-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c55ac-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c55ac-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c55ac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55ac-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c55ac-119">See also</span></span>

- [<span data-ttu-id="c55ac-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="c55ac-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
