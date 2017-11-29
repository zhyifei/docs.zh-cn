---
title: "CorDebugCreateProcessFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCreateProcessFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugCreateProcessFlags
helpviewer_keywords: CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35503a89077b05d622ccc3f8e5cf1bb7d95ea9e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="ffb19-102">CorDebugCreateProcessFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="ffb19-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="ffb19-103">提供了其他可以在调用中使用的调试选项[icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ffb19-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb19-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffb19-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ffb19-105">成员</span><span class="sxs-lookup"><span data-stu-id="ffb19-105">Members</span></span>  
  
|<span data-ttu-id="ffb19-106">成员</span><span class="sxs-lookup"><span data-stu-id="ffb19-106">Member</span></span>|<span data-ttu-id="ffb19-107">描述</span><span class="sxs-lookup"><span data-stu-id="ffb19-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="ffb19-108">不设置任何特殊的选项。</span><span class="sxs-lookup"><span data-stu-id="ffb19-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffb19-109">要求</span><span class="sxs-lookup"><span data-stu-id="ffb19-109">Requirements</span></span>  
 <span data-ttu-id="ffb19-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb19-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffb19-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffb19-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffb19-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffb19-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffb19-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffb19-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffb19-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffb19-114">See Also</span></span>  
 [<span data-ttu-id="ffb19-115">调试枚举</span><span class="sxs-lookup"><span data-stu-id="ffb19-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
