---
title: "“Cor调试解码事件标志窗口”枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDecodeEventFlagsWindows
api_location: mscordbi.dll
api_type: COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: facde76ec24d90795de7dfb70bfe5772a6f21531
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="cccfb-102">“Cor调试解码事件标志窗口”枚举</span><span class="sxs-lookup"><span data-stu-id="cccfb-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="cccfb-103">提供关于 Windows 平台上的调试事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="cccfb-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cccfb-104">语法</span><span class="sxs-lookup"><span data-stu-id="cccfb-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="cccfb-105">成员</span><span class="sxs-lookup"><span data-stu-id="cccfb-105">Members</span></span>  
  
|<span data-ttu-id="cccfb-106">成员</span><span class="sxs-lookup"><span data-stu-id="cccfb-106">Member</span></span>|<span data-ttu-id="cccfb-107">描述</span><span class="sxs-lookup"><span data-stu-id="cccfb-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="cccfb-108">指出调试事件为最可能的异常。</span><span class="sxs-lookup"><span data-stu-id="cccfb-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cccfb-109">备注</span><span class="sxs-lookup"><span data-stu-id="cccfb-109">Remarks</span></span>  
 <span data-ttu-id="cccfb-110">[Icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法包括`dwFlags`参数，它提供调试事件相关的其他信息，并且其值为依赖于目标体系结构。</span><span class="sxs-lookup"><span data-stu-id="cccfb-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="cccfb-111">`CorDebugDecodeEventFlagsWindows` 枚举可与 Windows 平台上的调试事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="cccfb-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cccfb-112">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="cccfb-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cccfb-113">要求</span><span class="sxs-lookup"><span data-stu-id="cccfb-113">Requirements</span></span>  
 <span data-ttu-id="cccfb-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cccfb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cccfb-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cccfb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cccfb-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cccfb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cccfb-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cccfb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccfb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cccfb-118">See Also</span></span>  
 [<span data-ttu-id="cccfb-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="cccfb-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
