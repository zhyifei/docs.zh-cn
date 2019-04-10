---
title: CorDebugHandleType 枚举
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513fc93bdac71e2a3ba59ebb53fdde44f1659af5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220456"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="3accd-102">CorDebugHandleType 枚举</span><span class="sxs-lookup"><span data-stu-id="3accd-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="3accd-103">指示句柄类型。</span><span class="sxs-lookup"><span data-stu-id="3accd-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3accd-104">语法</span><span class="sxs-lookup"><span data-stu-id="3accd-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="3accd-105">成员</span><span class="sxs-lookup"><span data-stu-id="3accd-105">Members</span></span>  
  
|<span data-ttu-id="3accd-106">成员</span><span class="sxs-lookup"><span data-stu-id="3accd-106">Member</span></span>|<span data-ttu-id="3accd-107">描述</span><span class="sxs-lookup"><span data-stu-id="3accd-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="3accd-108">句柄是强，这可防止垃圾回收功能回收对象。</span><span class="sxs-lookup"><span data-stu-id="3accd-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="3accd-109">句柄是弱，这不会阻止对象被垃圾回收期间回收。</span><span class="sxs-lookup"><span data-stu-id="3accd-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="3accd-110">当对象被收集时，该句柄将变为无效。</span><span class="sxs-lookup"><span data-stu-id="3accd-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3accd-111">要求</span><span class="sxs-lookup"><span data-stu-id="3accd-111">Requirements</span></span>  
 <span data-ttu-id="3accd-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3accd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3accd-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3accd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3accd-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3accd-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3accd-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3accd-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3accd-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3accd-116">See also</span></span>

- [<span data-ttu-id="3accd-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="3accd-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
