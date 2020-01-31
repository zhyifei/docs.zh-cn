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
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791340"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="2d08e-102">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="2d08e-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="2d08e-103">提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="2d08e-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d08e-104">方法</span><span class="sxs-lookup"><span data-stu-id="2d08e-104">Methods</span></span>  
  
|<span data-ttu-id="2d08e-105">方法</span><span class="sxs-lookup"><span data-stu-id="2d08e-105">Method</span></span>|<span data-ttu-id="2d08e-106">描述</span><span class="sxs-lookup"><span data-stu-id="2d08e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d08e-107">GetBlockingObjects 方法</span><span class="sxs-lookup"><span data-stu-id="2d08e-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="2d08e-108">提供[CorDebugBlockingObject](cordebugblockingobject-structure.md)结构的有序枚举，这些结构提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="2d08e-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="2d08e-109">HadUnhandledException 方法</span><span class="sxs-lookup"><span data-stu-id="2d08e-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="2d08e-110">指示线程是否曾经出现过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="2d08e-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="2d08e-111">GetCurrentCustomDebuggerNotification 方法</span><span class="sxs-lookup"><span data-stu-id="2d08e-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="2d08e-112">获取当前线程上的当前[ICorDebugManagedCallback3：： CustomNotification](icordebugmanagedcallback3-customnotification-method.md)对象。</span><span class="sxs-lookup"><span data-stu-id="2d08e-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d08e-113">备注</span><span class="sxs-lookup"><span data-stu-id="2d08e-113">Remarks</span></span>  
 <span data-ttu-id="2d08e-114">此接口是 ICorDebugThread、ICorDebugThread2 和[ICorDebugThread3](icordebugthread3-interface.md)接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="2d08e-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d08e-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2d08e-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d08e-116">需求</span><span class="sxs-lookup"><span data-stu-id="2d08e-116">Requirements</span></span>  
 <span data-ttu-id="2d08e-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d08e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d08e-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d08e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d08e-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d08e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d08e-120">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d08e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d08e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d08e-121">See also</span></span>

- [<span data-ttu-id="2d08e-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="2d08e-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2d08e-123">调试</span><span class="sxs-lookup"><span data-stu-id="2d08e-123">Debugging</span></span>](index.md)
