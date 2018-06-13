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
ms.openlocfilehash: 6fe5710f1be0bfa4e651668e2469c3551ad79261
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423827"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="c4b1d-102">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="c4b1d-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="c4b1d-103">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c4b1d-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4b1d-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="c4b1d-105">成员</span><span class="sxs-lookup"><span data-stu-id="c4b1d-105">Members</span></span>  
  
|<span data-ttu-id="c4b1d-106">成员</span><span class="sxs-lookup"><span data-stu-id="c4b1d-106">Member</span></span>|<span data-ttu-id="c4b1d-107">描述</span><span class="sxs-lookup"><span data-stu-id="c4b1d-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="c4b1d-108">创建调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="c4b1d-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="c4b1d-109">调试/跟踪开关已修改。</span><span class="sxs-lookup"><span data-stu-id="c4b1d-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="c4b1d-110">调试/跟踪开关已删除。</span><span class="sxs-lookup"><span data-stu-id="c4b1d-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4b1d-111">要求</span><span class="sxs-lookup"><span data-stu-id="c4b1d-111">Requirements</span></span>  
 <span data-ttu-id="c4b1d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b1d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b1d-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4b1d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4b1d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4b1d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4b1d-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b1d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b1d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b1d-116">See Also</span></span>  
 [<span data-ttu-id="c4b1d-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="c4b1d-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
