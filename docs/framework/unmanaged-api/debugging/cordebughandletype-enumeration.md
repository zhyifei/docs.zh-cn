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
ms.openlocfilehash: 15572037940f7c45ec5dcb7e34599756e15fd3bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793913"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="d1e2c-102">CorDebugHandleType 枚举</span><span class="sxs-lookup"><span data-stu-id="d1e2c-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="d1e2c-103">指示句柄类型。</span><span class="sxs-lookup"><span data-stu-id="d1e2c-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e2c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1e2c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="d1e2c-105">Members</span><span class="sxs-lookup"><span data-stu-id="d1e2c-105">Members</span></span>  
  
|<span data-ttu-id="d1e2c-106">成员</span><span class="sxs-lookup"><span data-stu-id="d1e2c-106">Member</span></span>|<span data-ttu-id="d1e2c-107">描述</span><span class="sxs-lookup"><span data-stu-id="d1e2c-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="d1e2c-108">句柄是强的，这会阻止垃圾回收功能回收对象。</span><span class="sxs-lookup"><span data-stu-id="d1e2c-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="d1e2c-109">句柄是弱的，不会阻止垃圾回收来回收对象。</span><span class="sxs-lookup"><span data-stu-id="d1e2c-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="d1e2c-110">收集对象时句柄变为无效。</span><span class="sxs-lookup"><span data-stu-id="d1e2c-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1e2c-111">需求</span><span class="sxs-lookup"><span data-stu-id="d1e2c-111">Requirements</span></span>  
 <span data-ttu-id="d1e2c-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1e2c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e2c-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1e2c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1e2c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1e2c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1e2c-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e2c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e2c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1e2c-116">See also</span></span>

- [<span data-ttu-id="d1e2c-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="d1e2c-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
