---
title: COR_SEGMENT 结构
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deea4e6128eace0ffa539d77bb63f7629eb72354
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207399"
---
# <a name="corsegment-structure"></a><span data-ttu-id="26cf0-102">COR_SEGMENT 结构</span><span class="sxs-lookup"><span data-stu-id="26cf0-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="26cf0-103">包含有关托管堆中的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="26cf0-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26cf0-104">语法</span><span class="sxs-lookup"><span data-stu-id="26cf0-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="26cf0-105">成员</span><span class="sxs-lookup"><span data-stu-id="26cf0-105">Members</span></span>  
  
|<span data-ttu-id="26cf0-106">成员</span><span class="sxs-lookup"><span data-stu-id="26cf0-106">Member</span></span>|<span data-ttu-id="26cf0-107">描述</span><span class="sxs-lookup"><span data-stu-id="26cf0-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="26cf0-108">内存区域的起始地址。</span><span class="sxs-lookup"><span data-stu-id="26cf0-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="26cf0-109">内存区域的结束地址。</span><span class="sxs-lookup"><span data-stu-id="26cf0-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="26cf0-110">显示内存区域生成的 [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) 枚举成员。</span><span class="sxs-lookup"><span data-stu-id="26cf0-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="26cf0-111">内存区域驻留的堆数。</span><span class="sxs-lookup"><span data-stu-id="26cf0-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="26cf0-112">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="26cf0-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26cf0-113">备注</span><span class="sxs-lookup"><span data-stu-id="26cf0-113">Remarks</span></span>  
 <span data-ttu-id="26cf0-114">`COR_SEGMENTS` 结构表示托管堆中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="26cf0-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="26cf0-115">`COR_SEGMENTS` 对象是 [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) 集合对象的成员，通过调用 [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) 方法填充。</span><span class="sxs-lookup"><span data-stu-id="26cf0-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="26cf0-116">`heap` 字段是处理器编号，对应报告的堆。</span><span class="sxs-lookup"><span data-stu-id="26cf0-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="26cf0-117">对于工作站垃圾回收器，其值始终为零，因为工作站仅有一个垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="26cf0-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="26cf0-118">对于服务器垃圾回收器，其值对应于堆附加到的处理器。</span><span class="sxs-lookup"><span data-stu-id="26cf0-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="26cf0-119">请注意，根据垃圾回收器的实现细节，垃圾回收堆可能多于或少于实际的处理器。</span><span class="sxs-lookup"><span data-stu-id="26cf0-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26cf0-120">要求</span><span class="sxs-lookup"><span data-stu-id="26cf0-120">Requirements</span></span>  
 <span data-ttu-id="26cf0-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26cf0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26cf0-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26cf0-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26cf0-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26cf0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26cf0-124">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26cf0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26cf0-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="26cf0-125">See Also</span></span>  
 [<span data-ttu-id="26cf0-126">调试结构</span><span class="sxs-lookup"><span data-stu-id="26cf0-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="26cf0-127">调试</span><span class="sxs-lookup"><span data-stu-id="26cf0-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
