---
title: "CorDebugStepReason 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStepReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugStepReason
helpviewer_keywords: CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32892a14de820e8add38654cef92aa44930aec62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="21431-102">CorDebugStepReason 枚举</span><span class="sxs-lookup"><span data-stu-id="21431-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="21431-103">指示一个单步执行的结果。</span><span class="sxs-lookup"><span data-stu-id="21431-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21431-104">语法</span><span class="sxs-lookup"><span data-stu-id="21431-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="21431-105">成员</span><span class="sxs-lookup"><span data-stu-id="21431-105">Members</span></span>  
  
|<span data-ttu-id="21431-106">成员</span><span class="sxs-lookup"><span data-stu-id="21431-106">Member</span></span>|<span data-ttu-id="21431-107">描述</span><span class="sxs-lookup"><span data-stu-id="21431-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="21431-108">在同一函数中通常情况下，完成单步执行。</span><span class="sxs-lookup"><span data-stu-id="21431-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="21431-109">继续单步执行正常情况下，该函数返回之后。</span><span class="sxs-lookup"><span data-stu-id="21431-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="21431-110">开头的新调用的函数通常情况下，继续单步执行。</span><span class="sxs-lookup"><span data-stu-id="21431-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="21431-111">生成了异常，控件已传递给异常筛选器。</span><span class="sxs-lookup"><span data-stu-id="21431-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="21431-112">生成了异常，控制权已传递到异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="21431-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="21431-113">控件传递到侦听器。</span><span class="sxs-lookup"><span data-stu-id="21431-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="21431-114">线程退出之前完成该步骤。</span><span class="sxs-lookup"><span data-stu-id="21431-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21431-115">要求</span><span class="sxs-lookup"><span data-stu-id="21431-115">Requirements</span></span>  
 <span data-ttu-id="21431-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21431-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21431-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21431-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21431-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21431-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21431-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21431-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21431-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21431-120">See Also</span></span>  
 [<span data-ttu-id="21431-121">StepComplete 方法</span><span class="sxs-lookup"><span data-stu-id="21431-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="21431-122">调试枚举</span><span class="sxs-lookup"><span data-stu-id="21431-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
