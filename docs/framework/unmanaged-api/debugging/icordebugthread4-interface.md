---
title: "ICorDebugThread4 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4
helpviewer_keywords: ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0066fbda63e46442cc6b6b6547ad7f0393815840
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="91a91-102">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="91a91-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="91a91-103">提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="91a91-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91a91-104">方法</span><span class="sxs-lookup"><span data-stu-id="91a91-104">Methods</span></span>  
  
|<span data-ttu-id="91a91-105">方法</span><span class="sxs-lookup"><span data-stu-id="91a91-105">Method</span></span>|<span data-ttu-id="91a91-106">描述</span><span class="sxs-lookup"><span data-stu-id="91a91-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91a91-107">GetBlockingObjects 方法</span><span class="sxs-lookup"><span data-stu-id="91a91-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="91a91-108">提供的有序的枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构，并提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="91a91-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="91a91-109">HadUnhandledException 方法</span><span class="sxs-lookup"><span data-stu-id="91a91-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="91a91-110">指示线程是否曾有过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="91a91-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="91a91-111">GetCurrentCustomDebuggerNotification 方法</span><span class="sxs-lookup"><span data-stu-id="91a91-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="91a91-112">获取当前[icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)当前线程上的对象。</span><span class="sxs-lookup"><span data-stu-id="91a91-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91a91-113">备注</span><span class="sxs-lookup"><span data-stu-id="91a91-113">Remarks</span></span>  
 <span data-ttu-id="91a91-114">此接口是 ICorDebugThread，ICorDebugThread2 的逻辑扩展和[ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="91a91-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91a91-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="91a91-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a91-116">惠?</span><span class="sxs-lookup"><span data-stu-id="91a91-116">Requirements</span></span>  
 <span data-ttu-id="91a91-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91a91-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a91-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91a91-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91a91-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91a91-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91a91-120">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a91-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a91-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="91a91-121">See Also</span></span>  
 [<span data-ttu-id="91a91-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="91a91-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="91a91-123">调试</span><span class="sxs-lookup"><span data-stu-id="91a91-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
