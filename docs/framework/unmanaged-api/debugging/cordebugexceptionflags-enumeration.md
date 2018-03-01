---
title: "CorDebugExceptionFlags 枚举"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1b25211c8e7f03cc09e8729abc44af39f0c84259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="1e7b3-102">CorDebugExceptionFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="1e7b3-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="1e7b3-103">提供有关异常的附加信息。</span><span class="sxs-lookup"><span data-stu-id="1e7b3-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e7b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e7b3-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1e7b3-105">成员</span><span class="sxs-lookup"><span data-stu-id="1e7b3-105">Members</span></span>  
  
|<span data-ttu-id="1e7b3-106">成员</span><span class="sxs-lookup"><span data-stu-id="1e7b3-106">Member</span></span>|<span data-ttu-id="1e7b3-107">描述</span><span class="sxs-lookup"><span data-stu-id="1e7b3-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="1e7b3-108">没有异常。</span><span class="sxs-lookup"><span data-stu-id="1e7b3-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="1e7b3-109">异常是可截获的。</span><span class="sxs-lookup"><span data-stu-id="1e7b3-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="1e7b3-110">异常的发生时间可能仍然会使调试器无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="1e7b3-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="1e7b3-111">例如，如果当前回调或实时 (JIT) 连接引起的异常事件下没有托管代码，则无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="1e7b3-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e7b3-112">备注</span><span class="sxs-lookup"><span data-stu-id="1e7b3-112">Remarks</span></span>  
 <span data-ttu-id="1e7b3-113">以后的版本可能会向此枚举中添加新值，因此你应针对意外值准备使用 `CorDebugExceptionFlags` 的代码。</span><span class="sxs-lookup"><span data-stu-id="1e7b3-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e7b3-114">惠?</span><span class="sxs-lookup"><span data-stu-id="1e7b3-114">Requirements</span></span>  
 <span data-ttu-id="1e7b3-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7b3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e7b3-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e7b3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e7b3-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e7b3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e7b3-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e7b3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7b3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e7b3-119">See Also</span></span>  
 [<span data-ttu-id="1e7b3-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="1e7b3-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
