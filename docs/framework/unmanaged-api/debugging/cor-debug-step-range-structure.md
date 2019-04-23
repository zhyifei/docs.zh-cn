---
title: COR_DEBUG_STEP_RANGE 结构
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d7c3256d7b52a4e55dbb5bc420b0438983d2f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219676"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="e800d-102">COR_DEBUG_STEP_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="e800d-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="e800d-103">包含代码区域的偏离量信息。</span><span class="sxs-lookup"><span data-stu-id="e800d-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="e800d-104">此结构可供[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e800d-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e800d-105">语法</span><span class="sxs-lookup"><span data-stu-id="e800d-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="e800d-106">成员</span><span class="sxs-lookup"><span data-stu-id="e800d-106">Members</span></span>  
  
|<span data-ttu-id="e800d-107">成员</span><span class="sxs-lookup"><span data-stu-id="e800d-107">Member</span></span>|<span data-ttu-id="e800d-108">描述</span><span class="sxs-lookup"><span data-stu-id="e800d-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="e800d-109">范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="e800d-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="e800d-110">范围末尾的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e800d-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e800d-111">要求</span><span class="sxs-lookup"><span data-stu-id="e800d-111">Requirements</span></span>  
 <span data-ttu-id="e800d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e800d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e800d-113">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="e800d-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="e800d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e800d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e800d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e800d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e800d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e800d-116">See also</span></span>

- [<span data-ttu-id="e800d-117">StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="e800d-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)
- [<span data-ttu-id="e800d-118">调试结构</span><span class="sxs-lookup"><span data-stu-id="e800d-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="e800d-119">调试</span><span class="sxs-lookup"><span data-stu-id="e800d-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
