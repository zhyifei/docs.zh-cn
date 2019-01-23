---
title: CorDebugGuidToTypeMapping 结构
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49290a37ca7ea101e3c8b458a5daa4995cb3beee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610040"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="e4e31-102">CorDebugGuidToTypeMapping 结构</span><span class="sxs-lookup"><span data-stu-id="e4e31-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="e4e31-103">映射[!INCLUDE[wrt](../../../../includes/wrt-md.md)]GUID 传递给其相应的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="e4e31-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4e31-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4e31-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="e4e31-105">成员</span><span class="sxs-lookup"><span data-stu-id="e4e31-105">Members</span></span>  
  
|<span data-ttu-id="e4e31-106">成员</span><span class="sxs-lookup"><span data-stu-id="e4e31-106">Member</span></span>|<span data-ttu-id="e4e31-107">描述</span><span class="sxs-lookup"><span data-stu-id="e4e31-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="e4e31-108">已缓存的 GUID[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="e4e31-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="e4e31-109">指向一个 ICorDebugType 对象，提供有关缓存类型的信息的指针。</span><span class="sxs-lookup"><span data-stu-id="e4e31-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4e31-110">要求</span><span class="sxs-lookup"><span data-stu-id="e4e31-110">Requirements</span></span>  
 <span data-ttu-id="e4e31-111">**平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e4e31-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="e4e31-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4e31-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4e31-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4e31-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4e31-114">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4e31-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e31-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4e31-115">See also</span></span>
- [<span data-ttu-id="e4e31-116">调试结构</span><span class="sxs-lookup"><span data-stu-id="e4e31-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="e4e31-117">调试</span><span class="sxs-lookup"><span data-stu-id="e4e31-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
