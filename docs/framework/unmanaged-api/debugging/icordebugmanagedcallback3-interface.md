---
title: "ICorDebugManagedCallback3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a517a9557f84b7eac5d9a773b85ffc7605eba8c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="ec9df-102">ICorDebugManagedCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="ec9df-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="ec9df-103">提供一个回调方法，该方法指示已发出启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="ec9df-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec9df-104">方法</span><span class="sxs-lookup"><span data-stu-id="ec9df-104">Methods</span></span>  
  
|<span data-ttu-id="ec9df-105">方法</span><span class="sxs-lookup"><span data-stu-id="ec9df-105">Method</span></span>|<span data-ttu-id="ec9df-106">描述</span><span class="sxs-lookup"><span data-stu-id="ec9df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec9df-107">CustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="ec9df-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="ec9df-108">指示已发出启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="ec9df-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec9df-109">备注</span><span class="sxs-lookup"><span data-stu-id="ec9df-109">Remarks</span></span>  
 <span data-ttu-id="ec9df-110">此接口是的逻辑扩展[ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)和[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ec9df-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec9df-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ec9df-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec9df-112">惠?</span><span class="sxs-lookup"><span data-stu-id="ec9df-112">Requirements</span></span>  
 <span data-ttu-id="ec9df-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec9df-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec9df-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec9df-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec9df-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec9df-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec9df-116">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec9df-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec9df-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec9df-117">See Also</span></span>  
 [<span data-ttu-id="ec9df-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ec9df-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 [<span data-ttu-id="ec9df-119">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="ec9df-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="ec9df-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="ec9df-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ec9df-121">调试</span><span class="sxs-lookup"><span data-stu-id="ec9df-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
