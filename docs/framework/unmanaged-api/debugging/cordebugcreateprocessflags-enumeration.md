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
ms.openlocfilehash: c0e4c43ac18b5e214d38dd7a57452a3871e4b43d
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796023"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="6fc9d-102">CorDebugCreateProcessFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="6fc9d-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="6fc9d-103">提供可在对[ICorDebug：： CreateProcess](icordebug-createprocess-method.md)方法的调用中使用的其他调试选项。</span><span class="sxs-lookup"><span data-stu-id="6fc9d-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fc9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6fc9d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6fc9d-105">成员</span><span class="sxs-lookup"><span data-stu-id="6fc9d-105">Members</span></span>  
  
|<span data-ttu-id="6fc9d-106">成员</span><span class="sxs-lookup"><span data-stu-id="6fc9d-106">Member</span></span>|<span data-ttu-id="6fc9d-107">说明</span><span class="sxs-lookup"><span data-stu-id="6fc9d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="6fc9d-108">未设置任何特殊选项。</span><span class="sxs-lookup"><span data-stu-id="6fc9d-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fc9d-109">要求</span><span class="sxs-lookup"><span data-stu-id="6fc9d-109">Requirements</span></span>  
 <span data-ttu-id="6fc9d-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc9d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fc9d-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fc9d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fc9d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fc9d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fc9d-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fc9d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc9d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fc9d-114">See also</span></span>

- [<span data-ttu-id="6fc9d-115">调试枚举</span><span class="sxs-lookup"><span data-stu-id="6fc9d-115">Debugging Enumerations</span></span>](debugging-enumerations.md)
