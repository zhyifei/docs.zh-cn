---
title: "“Cor调试状态已更改”枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStateChange
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: caf49621342be0ff85ac3cb56b95bb87f524c3be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="36505-102">“Cor调试状态已更改”枚举</span><span class="sxs-lookup"><span data-stu-id="36505-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="36505-103">描述基于进程变化必须删除的缓存数据数量。</span><span class="sxs-lookup"><span data-stu-id="36505-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36505-104">语法</span><span class="sxs-lookup"><span data-stu-id="36505-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="36505-105">成员</span><span class="sxs-lookup"><span data-stu-id="36505-105">Members</span></span>  
  
|<span data-ttu-id="36505-106">成员</span><span class="sxs-lookup"><span data-stu-id="36505-106">Member</span></span>|<span data-ttu-id="36505-107">描述</span><span class="sxs-lookup"><span data-stu-id="36505-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="36505-108">该进程向前执行，达到了一种新的内存状态。</span><span class="sxs-lookup"><span data-stu-id="36505-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="36505-109">进程的内存可能与以往截然不同。</span><span class="sxs-lookup"><span data-stu-id="36505-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36505-110">备注</span><span class="sxs-lookup"><span data-stu-id="36505-110">Remarks</span></span>  
 <span data-ttu-id="36505-111">成员`CorDebugStateChange`当调试器调用时，作为参数提供的枚举[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)方法</span><span class="sxs-lookup"><span data-stu-id="36505-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36505-112">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="36505-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36505-113">要求</span><span class="sxs-lookup"><span data-stu-id="36505-113">Requirements</span></span>  
 <span data-ttu-id="36505-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36505-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36505-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36505-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36505-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36505-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36505-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36505-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36505-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36505-118">See Also</span></span>  
 [<span data-ttu-id="36505-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="36505-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="36505-120">调试</span><span class="sxs-lookup"><span data-stu-id="36505-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
