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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ce2b23306e7e38f3982f8d5a4b377aa2f9547c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186246"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="a6ed9-102">CorDebugStepReason 枚举</span><span class="sxs-lookup"><span data-stu-id="a6ed9-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="a6ed9-103">指示一个单步执行的结果。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ed9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6ed9-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="a6ed9-105">成员</span><span class="sxs-lookup"><span data-stu-id="a6ed9-105">Members</span></span>  
  
|<span data-ttu-id="a6ed9-106">成员</span><span class="sxs-lookup"><span data-stu-id="a6ed9-106">Member</span></span>|<span data-ttu-id="a6ed9-107">描述</span><span class="sxs-lookup"><span data-stu-id="a6ed9-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="a6ed9-108">单步执行已完成正常情况下，同一函数中。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="a6ed9-109">继续单步执行通常情况下，该函数返回后。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="a6ed9-110">新被调用函数的开头通常情况下，继续单步执行。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="a6ed9-111">生成了异常，控制已传递给异常筛选器。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="a6ed9-112">生成了异常，控制已传递到异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="a6ed9-113">控件传递到侦听器。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="a6ed9-114">线程退出之前完成该步骤。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6ed9-115">要求</span><span class="sxs-lookup"><span data-stu-id="a6ed9-115">Requirements</span></span>  
 <span data-ttu-id="a6ed9-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6ed9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ed9-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6ed9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6ed9-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6ed9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6ed9-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ed9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ed9-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6ed9-120">See also</span></span>

- [<span data-ttu-id="a6ed9-121">StepComplete 方法</span><span class="sxs-lookup"><span data-stu-id="a6ed9-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="a6ed9-122">调试枚举</span><span class="sxs-lookup"><span data-stu-id="a6ed9-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
