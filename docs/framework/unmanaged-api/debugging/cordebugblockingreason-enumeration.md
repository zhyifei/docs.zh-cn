---
title: CorDebugBlockingReason 枚举
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c867945f8a75cade5c7405b2908e2819f5d261d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706967"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="3c5f7-102">CorDebugBlockingReason 枚举</span><span class="sxs-lookup"><span data-stu-id="3c5f7-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="3c5f7-103">指定线程可能在给定对象上受到阻塞的原因。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c5f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c5f7-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="3c5f7-105">成员</span><span class="sxs-lookup"><span data-stu-id="3c5f7-105">Members</span></span>  
  
|<span data-ttu-id="3c5f7-106">成员</span><span class="sxs-lookup"><span data-stu-id="3c5f7-106">Member</span></span>|<span data-ttu-id="3c5f7-107">描述</span><span class="sxs-lookup"><span data-stu-id="3c5f7-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="3c5f7-108">仅限内部使用。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="3c5f7-109">一个线程尝试获取对某个对象的监视器锁与相关联的关键部分。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="3c5f7-110">通常情况下，发生这种情况时调用的一个<xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>或<xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="3c5f7-111">线程正在等待的对象的监视器锁与相关联的事件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="3c5f7-112">通常情况下，发生这种情况时调用的一个<xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait`方法。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c5f7-113">备注</span><span class="sxs-lookup"><span data-stu-id="3c5f7-113">Remarks</span></span>  
 <span data-ttu-id="3c5f7-114">当`BLOCKING_MONITOR_CRITICAL_SECTION`或`BLOCKING_MONITOR_EVENT`中使用成员[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构，`pBlockingObject`结构指向一个表示要输入的对象的"ICorDebugValue"接口的成员.</span><span class="sxs-lookup"><span data-stu-id="3c5f7-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="3c5f7-115">它还保证以实现[ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c5f7-116">要求</span><span class="sxs-lookup"><span data-stu-id="3c5f7-116">Requirements</span></span>  
 <span data-ttu-id="3c5f7-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c5f7-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c5f7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c5f7-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c5f7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c5f7-120">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c5f7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5f7-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c5f7-121">See also</span></span>
- [<span data-ttu-id="3c5f7-122">调试枚举</span><span class="sxs-lookup"><span data-stu-id="3c5f7-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="3c5f7-123">调试</span><span class="sxs-lookup"><span data-stu-id="3c5f7-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
