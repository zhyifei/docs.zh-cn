---
title: CorDebugCreateProcessFlags 枚举
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fdc37676bfae8ac90fde0a7a5b11037b8357e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403752"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="f51c9-102">CorDebugCreateProcessFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="f51c9-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="f51c9-103">提供了其他可以在调用中使用的调试选项[icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f51c9-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="f51c9-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f51c9-105">成员</span><span class="sxs-lookup"><span data-stu-id="f51c9-105">Members</span></span>  
  
|<span data-ttu-id="f51c9-106">成员</span><span class="sxs-lookup"><span data-stu-id="f51c9-106">Member</span></span>|<span data-ttu-id="f51c9-107">描述</span><span class="sxs-lookup"><span data-stu-id="f51c9-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="f51c9-108">不设置任何特殊的选项。</span><span class="sxs-lookup"><span data-stu-id="f51c9-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f51c9-109">要求</span><span class="sxs-lookup"><span data-stu-id="f51c9-109">Requirements</span></span>  
 <span data-ttu-id="f51c9-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f51c9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f51c9-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f51c9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f51c9-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f51c9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f51c9-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f51c9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51c9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f51c9-114">See Also</span></span>  
 [<span data-ttu-id="f51c9-115">调试枚举</span><span class="sxs-lookup"><span data-stu-id="f51c9-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
