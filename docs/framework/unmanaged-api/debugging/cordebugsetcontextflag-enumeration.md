---
title: "CorDebugSetContextFlag 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugSetContextFlag
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugSetContextFlag
helpviewer_keywords: CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27e9fd561da74a3b88015e7820c2cbbd56ab2a7a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="749e4-102">CorDebugSetContextFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="749e4-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="749e4-103">指示上下文是来自堆栈上的活动（或叶）帧，还是已通过从另一个帧展开来进行计算。</span><span class="sxs-lookup"><span data-stu-id="749e4-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="749e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="749e4-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="749e4-105">成员</span><span class="sxs-lookup"><span data-stu-id="749e4-105">Members</span></span>  
  
|<span data-ttu-id="749e4-106">成员</span><span class="sxs-lookup"><span data-stu-id="749e4-106">Member</span></span>|<span data-ttu-id="749e4-107">描述</span><span class="sxs-lookup"><span data-stu-id="749e4-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="749e4-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="749e4-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="749e4-109">上下文是线程的活动上下文。</span><span class="sxs-lookup"><span data-stu-id="749e4-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="749e4-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="749e4-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="749e4-111">已通过从另一个帧展开来计算上下文。</span><span class="sxs-lookup"><span data-stu-id="749e4-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="749e4-112">备注</span><span class="sxs-lookup"><span data-stu-id="749e4-112">Remarks</span></span>  
 <span data-ttu-id="749e4-113">`CorDebugSetContextFlag`提供使用的值[icordebugstackwalk:: Setcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="749e4-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="749e4-114">惠?</span><span class="sxs-lookup"><span data-stu-id="749e4-114">Requirements</span></span>  
 <span data-ttu-id="749e4-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="749e4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="749e4-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="749e4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="749e4-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="749e4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="749e4-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="749e4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749e4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="749e4-119">See Also</span></span>  
 [<span data-ttu-id="749e4-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="749e4-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="749e4-121">调试</span><span class="sxs-lookup"><span data-stu-id="749e4-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
