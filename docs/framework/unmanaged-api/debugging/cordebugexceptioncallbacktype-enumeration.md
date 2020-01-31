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
ms.openlocfilehash: 977b1608539a302c6a27a1b54cfb2ad687025fe6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789411"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="cc244-102">CorDebugExceptionCallbackType 枚举</span><span class="sxs-lookup"><span data-stu-id="cc244-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="cc244-103">指示从[ICorDebugManagedCallback2：： Exception](icordebugmanagedcallback2-exception-method.md)事件进行的回调类型。</span><span class="sxs-lookup"><span data-stu-id="cc244-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc244-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc244-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="cc244-105">Members</span><span class="sxs-lookup"><span data-stu-id="cc244-105">Members</span></span>  
  
|<span data-ttu-id="cc244-106">成员</span><span class="sxs-lookup"><span data-stu-id="cc244-106">Member</span></span>|<span data-ttu-id="cc244-107">描述</span><span class="sxs-lookup"><span data-stu-id="cc244-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="cc244-108">引发了异常。</span><span class="sxs-lookup"><span data-stu-id="cc244-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="cc244-109">异常 windup 进程输入了用户代码。</span><span class="sxs-lookup"><span data-stu-id="cc244-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="cc244-110">异常 windup 进程在用户代码中找到 `catch` 块。</span><span class="sxs-lookup"><span data-stu-id="cc244-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="cc244-111">异常未处理。</span><span class="sxs-lookup"><span data-stu-id="cc244-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc244-112">需求</span><span class="sxs-lookup"><span data-stu-id="cc244-112">Requirements</span></span>  
 <span data-ttu-id="cc244-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc244-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc244-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc244-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc244-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc244-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc244-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc244-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc244-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc244-117">See also</span></span>

- [<span data-ttu-id="cc244-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="cc244-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
