---
title: "LogSwitchCallReason 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LogSwitchCallReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: LogSwitchCallReason
helpviewer_keywords: LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dcd91001dfd823416b08ba49ba4ed12a2c4d058
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="033e1-102">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="033e1-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="033e1-103">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="033e1-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="033e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="033e1-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="033e1-105">成员</span><span class="sxs-lookup"><span data-stu-id="033e1-105">Members</span></span>  
  
|<span data-ttu-id="033e1-106">成员</span><span class="sxs-lookup"><span data-stu-id="033e1-106">Member</span></span>|<span data-ttu-id="033e1-107">描述</span><span class="sxs-lookup"><span data-stu-id="033e1-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="033e1-108">创建调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="033e1-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="033e1-109">调试/跟踪开关已修改。</span><span class="sxs-lookup"><span data-stu-id="033e1-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="033e1-110">调试/跟踪开关已删除。</span><span class="sxs-lookup"><span data-stu-id="033e1-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="033e1-111">惠?</span><span class="sxs-lookup"><span data-stu-id="033e1-111">Requirements</span></span>  
 <span data-ttu-id="033e1-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="033e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="033e1-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="033e1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="033e1-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="033e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="033e1-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="033e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="033e1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="033e1-116">See Also</span></span>  
 [<span data-ttu-id="033e1-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="033e1-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
