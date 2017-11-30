---
title: "COR_DEBUG_STEP_RANGE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_DEBUG_STEP_RANGE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_DEBUG_STEP_RANGE
helpviewer_keywords: COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a696b69cf08d15ecd39a87920ecaa1934c00578
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="fe3e9-102">COR_DEBUG_STEP_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="fe3e9-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="fe3e9-103">包含代码区域的偏离量信息。</span><span class="sxs-lookup"><span data-stu-id="fe3e9-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="fe3e9-104">此结构可由[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fe3e9-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe3e9-105">语法</span><span class="sxs-lookup"><span data-stu-id="fe3e9-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="fe3e9-106">成员</span><span class="sxs-lookup"><span data-stu-id="fe3e9-106">Members</span></span>  
  
|<span data-ttu-id="fe3e9-107">成员</span><span class="sxs-lookup"><span data-stu-id="fe3e9-107">Member</span></span>|<span data-ttu-id="fe3e9-108">描述</span><span class="sxs-lookup"><span data-stu-id="fe3e9-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="fe3e9-109">范围的开始处的偏移量。</span><span class="sxs-lookup"><span data-stu-id="fe3e9-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="fe3e9-110">偏移量范围的末尾。</span><span class="sxs-lookup"><span data-stu-id="fe3e9-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe3e9-111">要求</span><span class="sxs-lookup"><span data-stu-id="fe3e9-111">Requirements</span></span>  
 <span data-ttu-id="fe3e9-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe3e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe3e9-113">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="fe3e9-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="fe3e9-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe3e9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe3e9-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe3e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe3e9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe3e9-116">See Also</span></span>  
 [<span data-ttu-id="fe3e9-117">StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="fe3e9-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)  
 [<span data-ttu-id="fe3e9-118">调试结构</span><span class="sxs-lookup"><span data-stu-id="fe3e9-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="fe3e9-119">调试</span><span class="sxs-lookup"><span data-stu-id="fe3e9-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
