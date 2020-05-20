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
ms.openlocfilehash: 4d29bb3886ffb51e1dfb9654f4d70ef7c568fd43
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420703"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="fe918-102">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="fe918-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="fe918-103">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="fe918-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe918-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe918-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="fe918-105">成员</span><span class="sxs-lookup"><span data-stu-id="fe918-105">Members</span></span>  
  
|<span data-ttu-id="fe918-106">成员</span><span class="sxs-lookup"><span data-stu-id="fe918-106">Member</span></span>|<span data-ttu-id="fe918-107">描述</span><span class="sxs-lookup"><span data-stu-id="fe918-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="fe918-108">已创建调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="fe918-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="fe918-109">已修改调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="fe918-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="fe918-110">已删除调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="fe918-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe918-111">要求</span><span class="sxs-lookup"><span data-stu-id="fe918-111">Requirements</span></span>  
 <span data-ttu-id="fe918-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe918-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe918-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe918-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe918-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe918-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe918-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe918-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe918-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe918-116">See also</span></span>

- [<span data-ttu-id="fe918-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="fe918-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
