---
title: CorDebugUnmappedStop 枚举
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d812a452910913f169d4377bafa82e823c533d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="2bd76-102">CorDebugUnmappedStop 枚举</span><span class="sxs-lookup"><span data-stu-id="2bd76-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="2bd76-103">指定未映射代码的类型，这些代码可以中断分档器代码执行。</span><span class="sxs-lookup"><span data-stu-id="2bd76-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd76-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bd76-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="2bd76-105">成员</span><span class="sxs-lookup"><span data-stu-id="2bd76-105">Members</span></span>  
  
|<span data-ttu-id="2bd76-106">成员</span><span class="sxs-lookup"><span data-stu-id="2bd76-106">Member</span></span>|<span data-ttu-id="2bd76-107">描述</span><span class="sxs-lookup"><span data-stu-id="2bd76-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="2bd76-108">不要停止在任何类型的未映射代码。</span><span class="sxs-lookup"><span data-stu-id="2bd76-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="2bd76-109">停止在 prolog 代码中。</span><span class="sxs-lookup"><span data-stu-id="2bd76-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="2bd76-110">停止在 epilog 代码。</span><span class="sxs-lookup"><span data-stu-id="2bd76-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="2bd76-111">在没有映射信息的代码中停止时。</span><span class="sxs-lookup"><span data-stu-id="2bd76-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="2bd76-112">停止在不适合 prolog、 epilog、 无映射信息或非托管的类别的未映射代码。</span><span class="sxs-lookup"><span data-stu-id="2bd76-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="2bd76-113">非托管代码中停止。</span><span class="sxs-lookup"><span data-stu-id="2bd76-113">Stop in unmanaged code.</span></span> <span data-ttu-id="2bd76-114">此值才有效仅使用互操作调试。</span><span class="sxs-lookup"><span data-stu-id="2bd76-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="2bd76-115">在所有类型的非托管代码中停止时。</span><span class="sxs-lookup"><span data-stu-id="2bd76-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bd76-116">备注</span><span class="sxs-lookup"><span data-stu-id="2bd76-116">Remarks</span></span>  
 <span data-ttu-id="2bd76-117">使用[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)方法以设置指定将在其中停止分档器未映射的代码的标志。</span><span class="sxs-lookup"><span data-stu-id="2bd76-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bd76-118">要求</span><span class="sxs-lookup"><span data-stu-id="2bd76-118">Requirements</span></span>  
 <span data-ttu-id="2bd76-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bd76-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bd76-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bd76-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bd76-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bd76-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bd76-122">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd76-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd76-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bd76-123">See Also</span></span>  
 [<span data-ttu-id="2bd76-124">调试枚举</span><span class="sxs-lookup"><span data-stu-id="2bd76-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
