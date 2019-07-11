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
ms.openlocfilehash: 894f74f12de7ed0754dcca34eacb815efc33c766
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752574"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="2b594-102">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="2b594-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="2b594-103">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2b594-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b594-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b594-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="2b594-105">成员</span><span class="sxs-lookup"><span data-stu-id="2b594-105">Members</span></span>  
  
|<span data-ttu-id="2b594-106">成员</span><span class="sxs-lookup"><span data-stu-id="2b594-106">Member</span></span>|<span data-ttu-id="2b594-107">描述</span><span class="sxs-lookup"><span data-stu-id="2b594-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="2b594-108">创建调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="2b594-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="2b594-109">调试/跟踪开关进行了修改。</span><span class="sxs-lookup"><span data-stu-id="2b594-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="2b594-110">调试/跟踪开关已删除。</span><span class="sxs-lookup"><span data-stu-id="2b594-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b594-111">要求</span><span class="sxs-lookup"><span data-stu-id="2b594-111">Requirements</span></span>  
 <span data-ttu-id="2b594-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b594-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b594-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b594-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b594-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b594-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b594-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b594-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b594-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b594-116">See also</span></span>

- [<span data-ttu-id="2b594-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="2b594-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
