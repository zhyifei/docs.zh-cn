---
title: "ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f13236c865f9a57d77ebf83ab48e010f06ef08e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="53db0-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法</span><span class="sxs-lookup"><span data-stu-id="53db0-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="53db0-103">[支持版本：[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 及更高版本]</span><span class="sxs-lookup"><span data-stu-id="53db0-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="53db0-104">启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="53db0-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53db0-105">语法</span><span class="sxs-lookup"><span data-stu-id="53db0-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53db0-106">参数</span><span class="sxs-lookup"><span data-stu-id="53db0-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="53db0-107">[in]</span><span class="sxs-lookup"><span data-stu-id="53db0-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53db0-108">备注</span><span class="sxs-lookup"><span data-stu-id="53db0-108">Remarks</span></span>  
 <span data-ttu-id="53db0-109">如果 `enableExceptionsOutsideOfJMC` 的值是 `false`：</span><span class="sxs-lookup"><span data-stu-id="53db0-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
-   <span data-ttu-id="53db0-110">DEBUG_EXCEPTION_FIRST_CHANCE 异常不会导致回调到调试器。</span><span class="sxs-lookup"><span data-stu-id="53db0-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
-   <span data-ttu-id="53db0-111">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 异常不会导致回调到调试器如果异常不会转义到用户代码 （即，从异常源到异常处理程序的路径具有标记为 JustMyCode 或 jmc 的方法没有方法）。</span><span class="sxs-lookup"><span data-stu-id="53db0-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="53db0-112">`enableExceptionsOutsideOfJMC` 的默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="53db0-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53db0-113">惠?</span><span class="sxs-lookup"><span data-stu-id="53db0-113">Requirements</span></span>  
 <span data-ttu-id="53db0-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53db0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53db0-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53db0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53db0-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53db0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53db0-117">**.NET framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53db0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53db0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="53db0-118">See Also</span></span>  
 [<span data-ttu-id="53db0-119">ICorDebugProcess8 接口</span><span class="sxs-lookup"><span data-stu-id="53db0-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [<span data-ttu-id="53db0-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="53db0-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
