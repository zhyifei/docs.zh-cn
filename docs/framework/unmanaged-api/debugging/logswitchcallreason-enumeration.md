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
ms.openlocfilehash: 29781666c106755f96f945325e3a8953bf93b211
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790351"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="3f183-102">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="3f183-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="3f183-103">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3f183-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f183-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f183-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="3f183-105">Members</span><span class="sxs-lookup"><span data-stu-id="3f183-105">Members</span></span>  
  
|<span data-ttu-id="3f183-106">成员</span><span class="sxs-lookup"><span data-stu-id="3f183-106">Member</span></span>|<span data-ttu-id="3f183-107">描述</span><span class="sxs-lookup"><span data-stu-id="3f183-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="3f183-108">已创建调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="3f183-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="3f183-109">已修改调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="3f183-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="3f183-110">已删除调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="3f183-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f183-111">需求</span><span class="sxs-lookup"><span data-stu-id="3f183-111">Requirements</span></span>  
 <span data-ttu-id="3f183-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f183-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f183-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f183-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f183-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f183-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f183-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f183-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f183-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f183-116">See also</span></span>

- [<span data-ttu-id="3f183-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="3f183-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
