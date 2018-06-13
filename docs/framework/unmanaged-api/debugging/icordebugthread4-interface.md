---
title: ICorDebugThread4 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf486be306e149e2350e7239884c8f05b84f3a86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422079"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="297b6-102">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="297b6-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="297b6-103">提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="297b6-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="297b6-104">方法</span><span class="sxs-lookup"><span data-stu-id="297b6-104">Methods</span></span>  
  
|<span data-ttu-id="297b6-105">方法</span><span class="sxs-lookup"><span data-stu-id="297b6-105">Method</span></span>|<span data-ttu-id="297b6-106">描述</span><span class="sxs-lookup"><span data-stu-id="297b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="297b6-107">GetBlockingObjects 方法</span><span class="sxs-lookup"><span data-stu-id="297b6-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="297b6-108">提供的有序的枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构，并提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="297b6-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="297b6-109">HadUnhandledException 方法</span><span class="sxs-lookup"><span data-stu-id="297b6-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="297b6-110">指示线程是否曾有过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="297b6-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="297b6-111">GetCurrentCustomDebuggerNotification 方法</span><span class="sxs-lookup"><span data-stu-id="297b6-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="297b6-112">获取当前[icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)当前线程上的对象。</span><span class="sxs-lookup"><span data-stu-id="297b6-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="297b6-113">备注</span><span class="sxs-lookup"><span data-stu-id="297b6-113">Remarks</span></span>  
 <span data-ttu-id="297b6-114">此接口是 ICorDebugThread，ICorDebugThread2 的逻辑扩展和[ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="297b6-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="297b6-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="297b6-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="297b6-116">要求</span><span class="sxs-lookup"><span data-stu-id="297b6-116">Requirements</span></span>  
 <span data-ttu-id="297b6-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="297b6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="297b6-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="297b6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="297b6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="297b6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="297b6-120">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="297b6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297b6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="297b6-121">See Also</span></span>  
 [<span data-ttu-id="297b6-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="297b6-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="297b6-123">调试</span><span class="sxs-lookup"><span data-stu-id="297b6-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
