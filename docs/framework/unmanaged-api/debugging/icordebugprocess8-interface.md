---
title: "ICorDebugProcess8 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8fba6d04a3d91cf51ce843230a36b1844a400381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess8-interface"></a><span data-ttu-id="8611d-102">ICorDebugProcess8 接口</span><span class="sxs-lookup"><span data-stu-id="8611d-102">ICorDebugProcess8 Interface</span></span>
<span data-ttu-id="8611d-103">[支持版本：[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 及更高版本]</span><span class="sxs-lookup"><span data-stu-id="8611d-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="8611d-104">合理扩展 ICorDebugProcess 接口以启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="8611d-104">Logically extends the ICorDebugProcess interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8611d-105">方法</span><span class="sxs-lookup"><span data-stu-id="8611d-105">Methods</span></span>  
  
|<span data-ttu-id="8611d-106">方法</span><span class="sxs-lookup"><span data-stu-id="8611d-106">Method</span></span>|<span data-ttu-id="8611d-107">描述</span><span class="sxs-lookup"><span data-stu-id="8611d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8611d-108">EnableExceptionCallbacksOutsideOfMyCode 方法</span><span class="sxs-lookup"><span data-stu-id="8611d-108">EnableExceptionCallbacksOutsideOfMyCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|<span data-ttu-id="8611d-109">启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。</span><span class="sxs-lookup"><span data-stu-id="8611d-109">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8611d-110">备注</span><span class="sxs-lookup"><span data-stu-id="8611d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8611d-111">要求</span><span class="sxs-lookup"><span data-stu-id="8611d-111">Requirements</span></span>  
 <span data-ttu-id="8611d-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8611d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8611d-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8611d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8611d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8611d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8611d-115">**.NET framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8611d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8611d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8611d-116">See Also</span></span>  
 [<span data-ttu-id="8611d-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="8611d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8611d-118">调试</span><span class="sxs-lookup"><span data-stu-id="8611d-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
