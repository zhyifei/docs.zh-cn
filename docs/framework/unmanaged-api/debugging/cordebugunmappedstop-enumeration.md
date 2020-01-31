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
ms.openlocfilehash: 23e168b0f322a580917c3fcfcb767a7d4d4628f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793888"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="893cd-102">CorDebugUnmappedStop 枚举</span><span class="sxs-lookup"><span data-stu-id="893cd-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="893cd-103">指定未映射代码的类型，这些代码可以中断分档器代码执行。</span><span class="sxs-lookup"><span data-stu-id="893cd-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="893cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="893cd-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="893cd-105">Members</span><span class="sxs-lookup"><span data-stu-id="893cd-105">Members</span></span>  
  
|<span data-ttu-id="893cd-106">成员</span><span class="sxs-lookup"><span data-stu-id="893cd-106">Member</span></span>|<span data-ttu-id="893cd-107">描述</span><span class="sxs-lookup"><span data-stu-id="893cd-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="893cd-108">请勿在任何类型的未映射代码中停止。</span><span class="sxs-lookup"><span data-stu-id="893cd-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="893cd-109">在 prolog 代码中停止。</span><span class="sxs-lookup"><span data-stu-id="893cd-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="893cd-110">在 epilog 代码中停止。</span><span class="sxs-lookup"><span data-stu-id="893cd-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="893cd-111">在没有映射信息的代码中停止。</span><span class="sxs-lookup"><span data-stu-id="893cd-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="893cd-112">在未映射的代码中停止，不适合 prolog、epilog、无映射-信息或非托管类别。</span><span class="sxs-lookup"><span data-stu-id="893cd-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="893cd-113">在非托管代码中停止。</span><span class="sxs-lookup"><span data-stu-id="893cd-113">Stop in unmanaged code.</span></span> <span data-ttu-id="893cd-114">此值仅适用于互操作调试。</span><span class="sxs-lookup"><span data-stu-id="893cd-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="893cd-115">在所有类型的未映射代码中停止。</span><span class="sxs-lookup"><span data-stu-id="893cd-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="893cd-116">备注</span><span class="sxs-lookup"><span data-stu-id="893cd-116">Remarks</span></span>  
 <span data-ttu-id="893cd-117">使用[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md)方法设置标志，这些标志指定分档器将停止的未映射代码。</span><span class="sxs-lookup"><span data-stu-id="893cd-117">Use the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="893cd-118">需求</span><span class="sxs-lookup"><span data-stu-id="893cd-118">Requirements</span></span>  
 <span data-ttu-id="893cd-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="893cd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="893cd-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="893cd-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="893cd-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="893cd-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="893cd-122">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="893cd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893cd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="893cd-123">See also</span></span>

- [<span data-ttu-id="893cd-124">调试枚举</span><span class="sxs-lookup"><span data-stu-id="893cd-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
