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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 352a45a33a109570f100e91a24cd44dc4f6780e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740145"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="69250-102">CorDebugExceptionFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="69250-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="69250-103">提供有关异常的附加信息。</span><span class="sxs-lookup"><span data-stu-id="69250-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69250-104">语法</span><span class="sxs-lookup"><span data-stu-id="69250-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="69250-105">成员</span><span class="sxs-lookup"><span data-stu-id="69250-105">Members</span></span>  
  
|<span data-ttu-id="69250-106">成员</span><span class="sxs-lookup"><span data-stu-id="69250-106">Member</span></span>|<span data-ttu-id="69250-107">描述</span><span class="sxs-lookup"><span data-stu-id="69250-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="69250-108">没有异常。</span><span class="sxs-lookup"><span data-stu-id="69250-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="69250-109">异常是可截获的。</span><span class="sxs-lookup"><span data-stu-id="69250-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="69250-110">异常的发生时间可能仍然会使调试器无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="69250-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="69250-111">例如，如果当前回调或实时 (JIT) 连接引起的异常事件下没有托管代码，则无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="69250-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69250-112">备注</span><span class="sxs-lookup"><span data-stu-id="69250-112">Remarks</span></span>  
 <span data-ttu-id="69250-113">以后的版本可能会向此枚举中添加新值，因此你应针对意外值准备使用 `CorDebugExceptionFlags` 的代码。</span><span class="sxs-lookup"><span data-stu-id="69250-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69250-114">要求</span><span class="sxs-lookup"><span data-stu-id="69250-114">Requirements</span></span>  
 <span data-ttu-id="69250-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69250-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69250-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69250-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69250-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69250-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69250-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69250-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69250-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="69250-119">See also</span></span>

- [<span data-ttu-id="69250-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="69250-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
