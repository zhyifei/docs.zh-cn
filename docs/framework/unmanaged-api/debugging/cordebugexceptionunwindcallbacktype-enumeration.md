---
title: "CorDebugExceptionUnwindCallbackType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionUnwindCallbackType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionUnwindCallbackType
helpviewer_keywords: CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c5ee074e55d0d407f89c778c579aa5c4ce03a10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="ebf2d-102">CorDebugExceptionUnwindCallbackType 枚举</span><span class="sxs-lookup"><span data-stu-id="ebf2d-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="ebf2d-103">指示在展开阶段正由回调发送信号的事件。</span><span class="sxs-lookup"><span data-stu-id="ebf2d-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="ebf2d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="ebf2d-105">成员</span><span class="sxs-lookup"><span data-stu-id="ebf2d-105">Members</span></span>  
  
|<span data-ttu-id="ebf2d-106">成员</span><span class="sxs-lookup"><span data-stu-id="ebf2d-106">Member</span></span>|<span data-ttu-id="ebf2d-107">描述</span><span class="sxs-lookup"><span data-stu-id="ebf2d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="ebf2d-108">展开过程开始。</span><span class="sxs-lookup"><span data-stu-id="ebf2d-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="ebf2d-109">该异常被截获。</span><span class="sxs-lookup"><span data-stu-id="ebf2d-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebf2d-110">惠?</span><span class="sxs-lookup"><span data-stu-id="ebf2d-110">Requirements</span></span>  
 <span data-ttu-id="ebf2d-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf2d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf2d-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebf2d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebf2d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebf2d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebf2d-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf2d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf2d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf2d-115">See Also</span></span>  
 [<span data-ttu-id="ebf2d-116">调试枚举</span><span class="sxs-lookup"><span data-stu-id="ebf2d-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
