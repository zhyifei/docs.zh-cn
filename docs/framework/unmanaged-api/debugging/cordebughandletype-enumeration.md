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
ms.openlocfilehash: 5a957a042875b546a18a17422f355b712756e91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098173"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="7028e-102">CorDebugHandleType 枚举</span><span class="sxs-lookup"><span data-stu-id="7028e-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="7028e-103">指示句柄类型。</span><span class="sxs-lookup"><span data-stu-id="7028e-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7028e-104">语法</span><span class="sxs-lookup"><span data-stu-id="7028e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="7028e-105">Members</span><span class="sxs-lookup"><span data-stu-id="7028e-105">Members</span></span>  
  
|<span data-ttu-id="7028e-106">成员</span><span class="sxs-lookup"><span data-stu-id="7028e-106">Member</span></span>|<span data-ttu-id="7028e-107">描述</span><span class="sxs-lookup"><span data-stu-id="7028e-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="7028e-108">句柄是强的，这会阻止垃圾回收功能回收对象。</span><span class="sxs-lookup"><span data-stu-id="7028e-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="7028e-109">句柄是弱的，不会阻止垃圾回收来回收对象。</span><span class="sxs-lookup"><span data-stu-id="7028e-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="7028e-110">收集对象时句柄变为无效。</span><span class="sxs-lookup"><span data-stu-id="7028e-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7028e-111">要求</span><span class="sxs-lookup"><span data-stu-id="7028e-111">Requirements</span></span>  
 <span data-ttu-id="7028e-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7028e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7028e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7028e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7028e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7028e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7028e-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7028e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7028e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7028e-116">See also</span></span>

- [<span data-ttu-id="7028e-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="7028e-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
