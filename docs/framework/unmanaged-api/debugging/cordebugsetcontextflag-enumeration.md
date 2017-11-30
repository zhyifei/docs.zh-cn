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
ms.openlocfilehash: 958ed303fab3dcb01fad2040dd06381e76fe5a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="f50a5-102">CorDebugSetContextFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="f50a5-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="f50a5-103">指示上下文是来自堆栈上的活动（或叶）帧，还是已通过从另一个帧展开来进行计算。</span><span class="sxs-lookup"><span data-stu-id="f50a5-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f50a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f50a5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="f50a5-105">成员</span><span class="sxs-lookup"><span data-stu-id="f50a5-105">Members</span></span>  
  
|<span data-ttu-id="f50a5-106">成员</span><span class="sxs-lookup"><span data-stu-id="f50a5-106">Member</span></span>|<span data-ttu-id="f50a5-107">描述</span><span class="sxs-lookup"><span data-stu-id="f50a5-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f50a5-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="f50a5-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="f50a5-109">上下文是线程的活动上下文。</span><span class="sxs-lookup"><span data-stu-id="f50a5-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="f50a5-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="f50a5-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="f50a5-111">已通过从另一个帧展开来计算上下文。</span><span class="sxs-lookup"><span data-stu-id="f50a5-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f50a5-112">备注</span><span class="sxs-lookup"><span data-stu-id="f50a5-112">Remarks</span></span>  
 <span data-ttu-id="f50a5-113">`CorDebugSetContextFlag`提供使用的值[icordebugstackwalk:: Setcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f50a5-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f50a5-114">要求</span><span class="sxs-lookup"><span data-stu-id="f50a5-114">Requirements</span></span>  
 <span data-ttu-id="f50a5-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f50a5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f50a5-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f50a5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f50a5-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f50a5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f50a5-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f50a5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50a5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f50a5-119">See Also</span></span>  
 [<span data-ttu-id="f50a5-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="f50a5-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="f50a5-121">调试</span><span class="sxs-lookup"><span data-stu-id="f50a5-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
