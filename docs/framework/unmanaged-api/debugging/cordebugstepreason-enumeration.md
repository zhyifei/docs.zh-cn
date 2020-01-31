---
title: CorDebugStepReason 枚举
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 92aee981aca3bac32c0ef264799e486315ca5103
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789259"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="0a2e9-102">CorDebugStepReason 枚举</span><span class="sxs-lookup"><span data-stu-id="0a2e9-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="0a2e9-103">指示一个单步执行的结果。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a2e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a2e9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="0a2e9-105">Members</span><span class="sxs-lookup"><span data-stu-id="0a2e9-105">Members</span></span>  
  
|<span data-ttu-id="0a2e9-106">成员</span><span class="sxs-lookup"><span data-stu-id="0a2e9-106">Member</span></span>|<span data-ttu-id="0a2e9-107">描述</span><span class="sxs-lookup"><span data-stu-id="0a2e9-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="0a2e9-108">单步执行在同一函数内正常完成。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="0a2e9-109">在函数返回后，按正常方式继续执行。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="0a2e9-110">在新调用的函数开始时以正常方式继续执行。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="0a2e9-111">已生成异常，并已将控制权传递给异常筛选器。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="0a2e9-112">已生成异常，并已将控制权传递给异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="0a2e9-113">控件已传递给侦听器。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="0a2e9-114">线程在步骤完成之前退出。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a2e9-115">需求</span><span class="sxs-lookup"><span data-stu-id="0a2e9-115">Requirements</span></span>  
 <span data-ttu-id="0a2e9-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a2e9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a2e9-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a2e9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a2e9-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a2e9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a2e9-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a2e9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a2e9-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a2e9-120">See also</span></span>

- [<span data-ttu-id="0a2e9-121">StepComplete 方法</span><span class="sxs-lookup"><span data-stu-id="0a2e9-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="0a2e9-122">调试枚举</span><span class="sxs-lookup"><span data-stu-id="0a2e9-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
