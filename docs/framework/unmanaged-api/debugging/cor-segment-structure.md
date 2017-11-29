---
title: "COR_SEGMENT 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_SEGMENT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_SEGMENT
helpviewer_keywords: COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc7a749f92149d7f0f5725aec6d90d72e0582c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corsegment-structure"></a><span data-ttu-id="8d429-102">COR_SEGMENT 结构</span><span class="sxs-lookup"><span data-stu-id="8d429-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="8d429-103">包含有关托管堆中的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="8d429-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d429-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d429-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="8d429-105">成员</span><span class="sxs-lookup"><span data-stu-id="8d429-105">Members</span></span>  
  
|<span data-ttu-id="8d429-106">成员</span><span class="sxs-lookup"><span data-stu-id="8d429-106">Member</span></span>|<span data-ttu-id="8d429-107">描述</span><span class="sxs-lookup"><span data-stu-id="8d429-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="8d429-108">内存区域的起始地址。</span><span class="sxs-lookup"><span data-stu-id="8d429-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="8d429-109">内存区域的结束地址。</span><span class="sxs-lookup"><span data-stu-id="8d429-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="8d429-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)指示内存区域的生成的枚举成员。</span><span class="sxs-lookup"><span data-stu-id="8d429-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="8d429-111">堆数驻留内存区域。</span><span class="sxs-lookup"><span data-stu-id="8d429-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="8d429-112">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="8d429-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d429-113">备注</span><span class="sxs-lookup"><span data-stu-id="8d429-113">Remarks</span></span>  
 <span data-ttu-id="8d429-114">`COR_SEGMENTS`结构表示托管堆中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="8d429-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="8d429-115">`COR_SEGMENTS`对象是的成员[ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)集合对象，通过调用填充[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8d429-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="8d429-116">`heap`字段是处理器数，它对应于正在报告堆。</span><span class="sxs-lookup"><span data-stu-id="8d429-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="8d429-117">对于工作站垃圾回收器，其值始终是零，因为工作站具有只有一个垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="8d429-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="8d429-118">对于服务器垃圾回收器，其值对应于堆附加到的处理器。</span><span class="sxs-lookup"><span data-stu-id="8d429-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="8d429-119">请注意，可能会出现更多或更少的垃圾回收堆多于实际处理器由于垃圾回收器的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="8d429-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d429-120">要求</span><span class="sxs-lookup"><span data-stu-id="8d429-120">Requirements</span></span>  
 <span data-ttu-id="8d429-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d429-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d429-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d429-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d429-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d429-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d429-124">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d429-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d429-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d429-125">See Also</span></span>  
 [<span data-ttu-id="8d429-126">调试结构</span><span class="sxs-lookup"><span data-stu-id="8d429-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="8d429-127">调试</span><span class="sxs-lookup"><span data-stu-id="8d429-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
