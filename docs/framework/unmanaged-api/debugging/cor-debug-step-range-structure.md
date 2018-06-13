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
ms.openlocfilehash: d5809221f2f31bc725c6a62fa5f8f91822f1c157
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407219"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="21b64-102">COR_DEBUG_STEP_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="21b64-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="21b64-103">包含代码区域的偏离量信息。</span><span class="sxs-lookup"><span data-stu-id="21b64-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="21b64-104">此结构可由[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="21b64-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21b64-105">语法</span><span class="sxs-lookup"><span data-stu-id="21b64-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="21b64-106">成员</span><span class="sxs-lookup"><span data-stu-id="21b64-106">Members</span></span>  
  
|<span data-ttu-id="21b64-107">成员</span><span class="sxs-lookup"><span data-stu-id="21b64-107">Member</span></span>|<span data-ttu-id="21b64-108">描述</span><span class="sxs-lookup"><span data-stu-id="21b64-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="21b64-109">范围的开始处的偏移量。</span><span class="sxs-lookup"><span data-stu-id="21b64-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="21b64-110">偏移量范围的末尾。</span><span class="sxs-lookup"><span data-stu-id="21b64-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21b64-111">要求</span><span class="sxs-lookup"><span data-stu-id="21b64-111">Requirements</span></span>  
 <span data-ttu-id="21b64-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21b64-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21b64-113">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="21b64-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="21b64-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21b64-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21b64-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21b64-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b64-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="21b64-116">See Also</span></span>  
 [<span data-ttu-id="21b64-117">StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="21b64-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)  
 [<span data-ttu-id="21b64-118">调试结构</span><span class="sxs-lookup"><span data-stu-id="21b64-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="21b64-119">调试</span><span class="sxs-lookup"><span data-stu-id="21b64-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
