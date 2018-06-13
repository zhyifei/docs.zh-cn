---
title: COR_HEAPINFO 结构
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fb1ae367c30bb038bfe25961e91f02f172f486c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405751"
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="1d7ff-102">COR_HEAPINFO 结构</span><span class="sxs-lookup"><span data-stu-id="1d7ff-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="1d7ff-103">提供有关垃圾回收堆的常规信息，包括它是否是可枚举的。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d7ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d7ff-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="1d7ff-105">成员</span><span class="sxs-lookup"><span data-stu-id="1d7ff-105">Members</span></span>  
  
|<span data-ttu-id="1d7ff-106">成员</span><span class="sxs-lookup"><span data-stu-id="1d7ff-106">Member</span></span>|<span data-ttu-id="1d7ff-107">描述</span><span class="sxs-lookup"><span data-stu-id="1d7ff-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="1d7ff-108">`true` 如果垃圾回收结构有效，并且可以枚举堆;，否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="1d7ff-109">以字节为单位，在目标体系结构的指针的大小。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="1d7ff-110">堆中进程的逻辑垃圾回收数。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="1d7ff-111">`TRUE` 如果并发启用 （后台） 垃圾回收;否则为`FALSE`。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="1d7ff-112">成员[CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)枚举，该值指示是否在工作站或服务器上运行垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d7ff-113">备注</span><span class="sxs-lookup"><span data-stu-id="1d7ff-113">Remarks</span></span>  
 <span data-ttu-id="1d7ff-114">实例`COR_HEAPINFO`结构返回通过调用[icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="1d7ff-115">枚举在垃圾回收堆上的对象之前, 你必须始终检查`areGCStructuresValid`字段以确保堆是可枚举的状态。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="1d7ff-116">有关详细信息，请参阅[icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d7ff-117">要求</span><span class="sxs-lookup"><span data-stu-id="1d7ff-117">Requirements</span></span>  
 <span data-ttu-id="1d7ff-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d7ff-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d7ff-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d7ff-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d7ff-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d7ff-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d7ff-121">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d7ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7ff-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d7ff-122">See Also</span></span>  
 [<span data-ttu-id="1d7ff-123">调试结构</span><span class="sxs-lookup"><span data-stu-id="1d7ff-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="1d7ff-124">调试</span><span class="sxs-lookup"><span data-stu-id="1d7ff-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
