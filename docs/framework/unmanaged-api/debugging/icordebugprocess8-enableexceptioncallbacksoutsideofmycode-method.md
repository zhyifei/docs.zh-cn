---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: e54dd051f0dbd9c1964d381c2e05189c375fa66d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210132"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="ad0e1-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法</span><span class="sxs-lookup"><span data-stu-id="ad0e1-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="ad0e1-103">[.NET Framework 4.6 及更高版本中支持]</span><span class="sxs-lookup"><span data-stu-id="ad0e1-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="ad0e1-104">启用或禁用某些类型的[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="ad0e1-104">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad0e1-105">语法</span><span class="sxs-lookup"><span data-stu-id="ad0e1-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad0e1-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad0e1-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="ad0e1-107">[in]</span><span class="sxs-lookup"><span data-stu-id="ad0e1-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad0e1-108">备注</span><span class="sxs-lookup"><span data-stu-id="ad0e1-108">Remarks</span></span>  
 <span data-ttu-id="ad0e1-109">如果 `enableExceptionsOutsideOfJMC` 的值是 `false`：</span><span class="sxs-lookup"><span data-stu-id="ad0e1-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="ad0e1-110">DEBUG_EXCEPTION_FIRST_CHANCE 异常将不会导致回调到调试器。</span><span class="sxs-lookup"><span data-stu-id="ad0e1-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="ad0e1-111">如果异常不会转义到用户代码（即从异常源到异常处理程序的路径没有被标记为 JustMyCode 或 JMC 的方法），则 DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 异常不会导致回调到调试器。</span><span class="sxs-lookup"><span data-stu-id="ad0e1-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="ad0e1-112">`enableExceptionsOutsideOfJMC` 的默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="ad0e1-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad0e1-113">要求</span><span class="sxs-lookup"><span data-stu-id="ad0e1-113">Requirements</span></span>  
 <span data-ttu-id="ad0e1-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad0e1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad0e1-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad0e1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad0e1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad0e1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad0e1-117">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad0e1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0e1-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad0e1-118">See also</span></span>

- [<span data-ttu-id="ad0e1-119">ICorDebugProcess8 接口</span><span class="sxs-lookup"><span data-stu-id="ad0e1-119">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="ad0e1-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="ad0e1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
