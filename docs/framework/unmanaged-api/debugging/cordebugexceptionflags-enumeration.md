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
ms.openlocfilehash: d963a478ee7ae42159a0eb8a4b41cf20ae663aa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405444"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="102e5-102">CorDebugExceptionFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="102e5-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="102e5-103">提供有关异常的附加信息。</span><span class="sxs-lookup"><span data-stu-id="102e5-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="102e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="102e5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="102e5-105">成员</span><span class="sxs-lookup"><span data-stu-id="102e5-105">Members</span></span>  
  
|<span data-ttu-id="102e5-106">成员</span><span class="sxs-lookup"><span data-stu-id="102e5-106">Member</span></span>|<span data-ttu-id="102e5-107">描述</span><span class="sxs-lookup"><span data-stu-id="102e5-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="102e5-108">没有异常。</span><span class="sxs-lookup"><span data-stu-id="102e5-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="102e5-109">异常是可截获的。</span><span class="sxs-lookup"><span data-stu-id="102e5-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="102e5-110">异常的发生时间可能仍然会使调试器无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="102e5-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="102e5-111">例如，如果当前回调或实时 (JIT) 连接引起的异常事件下没有托管代码，则无法截获异常。</span><span class="sxs-lookup"><span data-stu-id="102e5-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="102e5-112">备注</span><span class="sxs-lookup"><span data-stu-id="102e5-112">Remarks</span></span>  
 <span data-ttu-id="102e5-113">以后的版本可能会向此枚举中添加新值，因此你应针对意外值准备使用 `CorDebugExceptionFlags` 的代码。</span><span class="sxs-lookup"><span data-stu-id="102e5-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="102e5-114">要求</span><span class="sxs-lookup"><span data-stu-id="102e5-114">Requirements</span></span>  
 <span data-ttu-id="102e5-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="102e5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="102e5-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="102e5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="102e5-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="102e5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="102e5-118">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="102e5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102e5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="102e5-119">See Also</span></span>  
 [<span data-ttu-id="102e5-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="102e5-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
