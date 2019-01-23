---
title: LogSwitchCallReason 枚举
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba39446d9ca5164d98337e93e83725cfa503903
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515321"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="d6e6d-102">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="d6e6d-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="d6e6d-103">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d6e6d-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e6d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6e6d-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="d6e6d-105">成员</span><span class="sxs-lookup"><span data-stu-id="d6e6d-105">Members</span></span>  
  
|<span data-ttu-id="d6e6d-106">成员</span><span class="sxs-lookup"><span data-stu-id="d6e6d-106">Member</span></span>|<span data-ttu-id="d6e6d-107">描述</span><span class="sxs-lookup"><span data-stu-id="d6e6d-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="d6e6d-108">创建调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="d6e6d-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="d6e6d-109">调试/跟踪开关进行了修改。</span><span class="sxs-lookup"><span data-stu-id="d6e6d-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="d6e6d-110">调试/跟踪开关已删除。</span><span class="sxs-lookup"><span data-stu-id="d6e6d-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6e6d-111">要求</span><span class="sxs-lookup"><span data-stu-id="d6e6d-111">Requirements</span></span>  
 <span data-ttu-id="d6e6d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e6d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e6d-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e6d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e6d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e6d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e6d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e6d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e6d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6e6d-116">See also</span></span>
- [<span data-ttu-id="d6e6d-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="d6e6d-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
