---
title: CorDebugExceptionUnwindCallbackType 枚举
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408e72eeaa1dac83c45488d186425f30c6043280
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786368"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="6fd16-102">CorDebugExceptionUnwindCallbackType 枚举</span><span class="sxs-lookup"><span data-stu-id="6fd16-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="6fd16-103">指示在展开阶段正由回调发送信号的事件。</span><span class="sxs-lookup"><span data-stu-id="6fd16-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd16-104">语法</span><span class="sxs-lookup"><span data-stu-id="6fd16-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="6fd16-105">成员</span><span class="sxs-lookup"><span data-stu-id="6fd16-105">Members</span></span>  
  
|<span data-ttu-id="6fd16-106">成员</span><span class="sxs-lookup"><span data-stu-id="6fd16-106">Member</span></span>|<span data-ttu-id="6fd16-107">描述</span><span class="sxs-lookup"><span data-stu-id="6fd16-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="6fd16-108">展开过程开始。</span><span class="sxs-lookup"><span data-stu-id="6fd16-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="6fd16-109">该异常被截获。</span><span class="sxs-lookup"><span data-stu-id="6fd16-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fd16-110">要求</span><span class="sxs-lookup"><span data-stu-id="6fd16-110">Requirements</span></span>  
 <span data-ttu-id="6fd16-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6fd16-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd16-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fd16-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fd16-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fd16-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fd16-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd16-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd16-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fd16-115">See also</span></span>

- [<span data-ttu-id="6fd16-116">调试枚举</span><span class="sxs-lookup"><span data-stu-id="6fd16-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
