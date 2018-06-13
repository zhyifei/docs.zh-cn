---
title: “Cor调试状态已更改”枚举
ms.date: 03/30/2017
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 841108457293e3377ee87f9c7d7c6898340e51b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404341"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="2a968-102">“Cor调试状态已更改”枚举</span><span class="sxs-lookup"><span data-stu-id="2a968-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="2a968-103">描述基于进程变化必须删除的缓存数据数量。</span><span class="sxs-lookup"><span data-stu-id="2a968-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a968-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a968-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="2a968-105">成员</span><span class="sxs-lookup"><span data-stu-id="2a968-105">Members</span></span>  
  
|<span data-ttu-id="2a968-106">成员</span><span class="sxs-lookup"><span data-stu-id="2a968-106">Member</span></span>|<span data-ttu-id="2a968-107">描述</span><span class="sxs-lookup"><span data-stu-id="2a968-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="2a968-108">该进程向前执行，达到了一种新的内存状态。</span><span class="sxs-lookup"><span data-stu-id="2a968-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="2a968-109">进程的内存可能与以往截然不同。</span><span class="sxs-lookup"><span data-stu-id="2a968-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a968-110">备注</span><span class="sxs-lookup"><span data-stu-id="2a968-110">Remarks</span></span>  
 <span data-ttu-id="2a968-111">成员`CorDebugStateChange`当调试器调用时，作为参数提供的枚举[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)方法</span><span class="sxs-lookup"><span data-stu-id="2a968-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a968-112">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="2a968-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a968-113">要求</span><span class="sxs-lookup"><span data-stu-id="2a968-113">Requirements</span></span>  
 <span data-ttu-id="2a968-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a968-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a968-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a968-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a968-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a968-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a968-117">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a968-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a968-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a968-118">See Also</span></span>  
 [<span data-ttu-id="2a968-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="2a968-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="2a968-120">调试</span><span class="sxs-lookup"><span data-stu-id="2a968-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
