---
title: "ICorDebugHeapSegmentEnum::Next 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7f8e197bb5d31635e4abc8e8bc6e3d62eb7632be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="9c249-102">ICorDebugHeapSegmentEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="9c249-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="9c249-103">获取指定的数目的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)包含信息的托管堆的内存区域的实例。</span><span class="sxs-lookup"><span data-stu-id="9c249-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c249-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c249-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c249-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c249-105">Parameters</span></span>  
 <span data-ttu-id="9c249-106">celt</span><span class="sxs-lookup"><span data-stu-id="9c249-106">celt</span></span>  
 <span data-ttu-id="9c249-107">[in]要检索的段的数。</span><span class="sxs-lookup"><span data-stu-id="9c249-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="9c249-108">段</span><span class="sxs-lookup"><span data-stu-id="9c249-108">segments</span></span>  
 <span data-ttu-id="9c249-109">[out]一个指针，其中每个指向数组[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)提供托管堆中的内存地区的相关信息的对象。</span><span class="sxs-lookup"><span data-stu-id="9c249-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="9c249-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="9c249-110">pceltFetched</span></span>  
 <span data-ttu-id="9c249-111">[out]指向数[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)中实际返回的对象`segments`。</span><span class="sxs-lookup"><span data-stu-id="9c249-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="9c249-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="9c249-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c249-113">备注</span><span class="sxs-lookup"><span data-stu-id="9c249-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c249-114">惠?</span><span class="sxs-lookup"><span data-stu-id="9c249-114">Requirements</span></span>  
 <span data-ttu-id="9c249-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c249-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c249-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c249-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c249-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c249-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c249-118">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c249-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c249-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c249-119">See Also</span></span>  
 [<span data-ttu-id="9c249-120">ICorDebugHeapSegmentEnum 接口</span><span class="sxs-lookup"><span data-stu-id="9c249-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 [<span data-ttu-id="9c249-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="9c249-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
