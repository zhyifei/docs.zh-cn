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
ms.openlocfilehash: b97f29b94ed4fad6892697ca1c7ed4a20c99c03e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793273"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="fc887-102">ICorDebugManagedCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="fc887-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="fc887-103">提供一个回调方法，该方法指示已发出启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="fc887-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc887-104">方法</span><span class="sxs-lookup"><span data-stu-id="fc887-104">Methods</span></span>  
  
|<span data-ttu-id="fc887-105">方法</span><span class="sxs-lookup"><span data-stu-id="fc887-105">Method</span></span>|<span data-ttu-id="fc887-106">描述</span><span class="sxs-lookup"><span data-stu-id="fc887-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc887-107">CustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="fc887-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="fc887-108">指示已引发启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="fc887-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc887-109">备注</span><span class="sxs-lookup"><span data-stu-id="fc887-109">Remarks</span></span>  
 <span data-ttu-id="fc887-110">此接口是[ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)和[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="fc887-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc887-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="fc887-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc887-112">需求</span><span class="sxs-lookup"><span data-stu-id="fc887-112">Requirements</span></span>  
 <span data-ttu-id="fc887-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc887-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc887-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc887-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc887-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc887-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc887-116">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc887-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc887-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc887-117">See also</span></span>

- [<span data-ttu-id="fc887-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="fc887-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="fc887-119">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="fc887-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="fc887-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="fc887-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc887-121">调试</span><span class="sxs-lookup"><span data-stu-id="fc887-121">Debugging</span></span>](index.md)
