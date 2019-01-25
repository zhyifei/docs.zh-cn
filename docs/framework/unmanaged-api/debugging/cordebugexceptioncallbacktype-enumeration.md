---
title: CorDebugExceptionCallbackType 枚举
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e9a3b0320ac0be785f0823afef1819ab8a35eb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585544"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="8da27-102">CorDebugExceptionCallbackType 枚举</span><span class="sxs-lookup"><span data-stu-id="8da27-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="8da27-103">指示从进行回调的类型[ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)事件。</span><span class="sxs-lookup"><span data-stu-id="8da27-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da27-104">语法</span><span class="sxs-lookup"><span data-stu-id="8da27-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="8da27-105">成员</span><span class="sxs-lookup"><span data-stu-id="8da27-105">Members</span></span>  
  
|<span data-ttu-id="8da27-106">成员</span><span class="sxs-lookup"><span data-stu-id="8da27-106">Member</span></span>|<span data-ttu-id="8da27-107">描述</span><span class="sxs-lookup"><span data-stu-id="8da27-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="8da27-108">引发了异常。</span><span class="sxs-lookup"><span data-stu-id="8da27-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="8da27-109">异常终结进程进入用户代码。</span><span class="sxs-lookup"><span data-stu-id="8da27-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="8da27-110">找到异常终结进程`catch`阻止在用户代码中。</span><span class="sxs-lookup"><span data-stu-id="8da27-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="8da27-111">未处理异常。</span><span class="sxs-lookup"><span data-stu-id="8da27-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8da27-112">要求</span><span class="sxs-lookup"><span data-stu-id="8da27-112">Requirements</span></span>  
 <span data-ttu-id="8da27-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8da27-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8da27-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8da27-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8da27-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8da27-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8da27-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8da27-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da27-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8da27-117">See also</span></span>
- [<span data-ttu-id="8da27-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="8da27-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
