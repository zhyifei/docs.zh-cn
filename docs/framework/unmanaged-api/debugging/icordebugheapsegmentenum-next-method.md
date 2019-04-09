---
title: ICorDebugHeapSegmentEnum::Next 方法
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d260fa762033e86351577d46c770543300876869
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132543"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="91fad-102">ICorDebugHeapSegmentEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="91fad-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="91fad-103">获取指定的数目的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)包含托管堆的内存区域有关的信息的实例。</span><span class="sxs-lookup"><span data-stu-id="91fad-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91fad-104">语法</span><span class="sxs-lookup"><span data-stu-id="91fad-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91fad-105">参数</span><span class="sxs-lookup"><span data-stu-id="91fad-105">Parameters</span></span>  
 <span data-ttu-id="91fad-106">celt</span><span class="sxs-lookup"><span data-stu-id="91fad-106">celt</span></span>  
 <span data-ttu-id="91fad-107">[in]要检索的段的数目。</span><span class="sxs-lookup"><span data-stu-id="91fad-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="91fad-108">段</span><span class="sxs-lookup"><span data-stu-id="91fad-108">segments</span></span>  
 <span data-ttu-id="91fad-109">[out]一个指针，其中每个指向数组[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)提供托管堆中的内存区域有关的信息的对象。</span><span class="sxs-lookup"><span data-stu-id="91fad-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="91fad-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="91fad-110">pceltFetched</span></span>  
 <span data-ttu-id="91fad-111">[out]指向数[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)对象中实际返回`segments`。</span><span class="sxs-lookup"><span data-stu-id="91fad-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="91fad-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="91fad-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91fad-113">备注</span><span class="sxs-lookup"><span data-stu-id="91fad-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91fad-114">要求</span><span class="sxs-lookup"><span data-stu-id="91fad-114">Requirements</span></span>  
 <span data-ttu-id="91fad-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91fad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91fad-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91fad-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91fad-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91fad-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="91fad-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="91fad-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="91fad-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="91fad-119">See also</span></span>

- [<span data-ttu-id="91fad-120">ICorDebugHeapSegmentEnum 接口</span><span class="sxs-lookup"><span data-stu-id="91fad-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="91fad-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="91fad-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
