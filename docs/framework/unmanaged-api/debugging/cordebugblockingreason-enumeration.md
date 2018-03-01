---
title: "CorDebugBlockingReason 枚举"
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
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 84c09de4e0ce6e436c2c814c4cd9990db012d422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="25de6-102">CorDebugBlockingReason 枚举</span><span class="sxs-lookup"><span data-stu-id="25de6-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="25de6-103">指定线程可能在给定对象上受到阻塞的原因。</span><span class="sxs-lookup"><span data-stu-id="25de6-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25de6-104">语法</span><span class="sxs-lookup"><span data-stu-id="25de6-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="25de6-105">成员</span><span class="sxs-lookup"><span data-stu-id="25de6-105">Members</span></span>  
  
|<span data-ttu-id="25de6-106">成员</span><span class="sxs-lookup"><span data-stu-id="25de6-106">Member</span></span>|<span data-ttu-id="25de6-107">描述</span><span class="sxs-lookup"><span data-stu-id="25de6-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="25de6-108">仅限内部使用。</span><span class="sxs-lookup"><span data-stu-id="25de6-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="25de6-109">线程尝试获取对某个对象的监视器锁与相关联的关键部分。</span><span class="sxs-lookup"><span data-stu-id="25de6-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="25de6-110">通常情况下，发生这种情况时调用的一个<xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>或<xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="25de6-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="25de6-111">线程正在等待的对象的监视器锁与关联的事件。</span><span class="sxs-lookup"><span data-stu-id="25de6-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="25de6-112">通常情况下，发生这种情况时调用的一个<xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait`方法。</span><span class="sxs-lookup"><span data-stu-id="25de6-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25de6-113">备注</span><span class="sxs-lookup"><span data-stu-id="25de6-113">Remarks</span></span>  
 <span data-ttu-id="25de6-114">当`BLOCKING_MONITOR_CRITICAL_SECTION`或`BLOCKING_MONITOR_EVENT`成员使用在[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构， `pBlockingObject` "ICorDebugValue"接口，它表示正在输入对象的结构点的成员.</span><span class="sxs-lookup"><span data-stu-id="25de6-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="25de6-115">此外可以保证实现[ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="25de6-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25de6-116">惠?</span><span class="sxs-lookup"><span data-stu-id="25de6-116">Requirements</span></span>  
 <span data-ttu-id="25de6-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25de6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25de6-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25de6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25de6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25de6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25de6-120">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25de6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25de6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="25de6-121">See Also</span></span>  
 [<span data-ttu-id="25de6-122">调试枚举</span><span class="sxs-lookup"><span data-stu-id="25de6-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="25de6-123">调试</span><span class="sxs-lookup"><span data-stu-id="25de6-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
