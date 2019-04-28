---
title: ICorDebugManagedCallback3 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acab49097059081540ec364d7f134d31432988a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723246"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="bcc3c-102">ICorDebugManagedCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="bcc3c-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="bcc3c-103">提供一个回调方法，该方法指示已发出启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="bcc3c-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bcc3c-104">方法</span><span class="sxs-lookup"><span data-stu-id="bcc3c-104">Methods</span></span>  
  
|<span data-ttu-id="bcc3c-105">方法</span><span class="sxs-lookup"><span data-stu-id="bcc3c-105">Method</span></span>|<span data-ttu-id="bcc3c-106">描述</span><span class="sxs-lookup"><span data-stu-id="bcc3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bcc3c-107">CustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="bcc3c-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="bcc3c-108">指示已引发的已启用自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="bcc3c-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcc3c-109">备注</span><span class="sxs-lookup"><span data-stu-id="bcc3c-109">Remarks</span></span>  
 <span data-ttu-id="bcc3c-110">此接口为的逻辑扩展[ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)并[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="bcc3c-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcc3c-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="bcc3c-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcc3c-112">要求</span><span class="sxs-lookup"><span data-stu-id="bcc3c-112">Requirements</span></span>  
 <span data-ttu-id="bcc3c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc3c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcc3c-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcc3c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcc3c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcc3c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcc3c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcc3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc3c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc3c-117">See also</span></span>

- [<span data-ttu-id="bcc3c-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="bcc3c-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="bcc3c-119">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="bcc3c-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="bcc3c-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="bcc3c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bcc3c-121">调试</span><span class="sxs-lookup"><span data-stu-id="bcc3c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
