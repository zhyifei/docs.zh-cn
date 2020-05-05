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
ms.openlocfilehash: 2d296c1778e00c4c72e860e0705994518d1481e8
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795875"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="726c5-102">CorDebugHandleType 枚举</span><span class="sxs-lookup"><span data-stu-id="726c5-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="726c5-103">指示句柄类型。</span><span class="sxs-lookup"><span data-stu-id="726c5-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="726c5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="726c5-105">成员</span><span class="sxs-lookup"><span data-stu-id="726c5-105">Members</span></span>  
  
|<span data-ttu-id="726c5-106">成员</span><span class="sxs-lookup"><span data-stu-id="726c5-106">Member</span></span>|<span data-ttu-id="726c5-107">说明</span><span class="sxs-lookup"><span data-stu-id="726c5-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="726c5-108">句柄是强的，这会阻止垃圾回收功能回收对象。</span><span class="sxs-lookup"><span data-stu-id="726c5-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="726c5-109">句柄是弱的，不会阻止垃圾回收来回收对象。</span><span class="sxs-lookup"><span data-stu-id="726c5-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="726c5-110">收集对象时句柄变为无效。</span><span class="sxs-lookup"><span data-stu-id="726c5-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="726c5-111">要求</span><span class="sxs-lookup"><span data-stu-id="726c5-111">Requirements</span></span>  
 <span data-ttu-id="726c5-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="726c5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726c5-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="726c5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="726c5-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="726c5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="726c5-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726c5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="726c5-116">See also</span></span>

- [<span data-ttu-id="726c5-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="726c5-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
