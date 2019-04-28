---
title: CorDebugBlockingObject 结构
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12a114ea65aca544d653704cdfb01ed15d19c581
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609264"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="073e1-102">CorDebugBlockingObject 结构</span><span class="sxs-lookup"><span data-stu-id="073e1-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="073e1-103">定义一个阻塞线程的线程被阻塞的具体原因的对象。</span><span class="sxs-lookup"><span data-stu-id="073e1-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="073e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="073e1-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="073e1-105">成员</span><span class="sxs-lookup"><span data-stu-id="073e1-105">Members</span></span>  
  
|<span data-ttu-id="073e1-106">成员</span><span class="sxs-lookup"><span data-stu-id="073e1-106">Member</span></span>|<span data-ttu-id="073e1-107">描述</span><span class="sxs-lookup"><span data-stu-id="073e1-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="073e1-108">在其阻止线程对象。</span><span class="sxs-lookup"><span data-stu-id="073e1-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="073e1-109">此对象的有效期仅为当前同步状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="073e1-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="073e1-110">如果两个线程要阻止在相同的同步状态中对同一个对象，会按预期[icordebugvalue:: Getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)方法以返回相同的值。</span><span class="sxs-lookup"><span data-stu-id="073e1-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="073e1-111">但是，接口可能也可能不是等效的指针。</span><span class="sxs-lookup"><span data-stu-id="073e1-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="073e1-112">阻止操作之前的毫秒数将超时时间，或者值为无穷大，这表示它将不会超时。超时值指定时间阻止操作，而不是仍剩余的时间的总长度。</span><span class="sxs-lookup"><span data-stu-id="073e1-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="073e1-113">线程此对象上阻塞的原因。</span><span class="sxs-lookup"><span data-stu-id="073e1-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="073e1-114">备注</span><span class="sxs-lookup"><span data-stu-id="073e1-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="073e1-115">要求</span><span class="sxs-lookup"><span data-stu-id="073e1-115">Requirements</span></span>  
 <span data-ttu-id="073e1-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="073e1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="073e1-117">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="073e1-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="073e1-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="073e1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="073e1-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="073e1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="073e1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="073e1-120">See also</span></span>

- [<span data-ttu-id="073e1-121">调试结构</span><span class="sxs-lookup"><span data-stu-id="073e1-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="073e1-122">调试</span><span class="sxs-lookup"><span data-stu-id="073e1-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
