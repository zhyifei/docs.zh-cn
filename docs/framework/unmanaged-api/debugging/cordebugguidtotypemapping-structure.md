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
ms.openlocfilehash: 38e1b19d6340f559e6f8b7e0f7bc042a10df16c3
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025996"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="eeb82-102">CorDebugGuidToTypeMapping 结构</span><span class="sxs-lookup"><span data-stu-id="eeb82-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="eeb82-103">将 Windows 运行时 GUID 映射到其相应的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="eeb82-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb82-104">语法</span><span class="sxs-lookup"><span data-stu-id="eeb82-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="eeb82-105">成员</span><span class="sxs-lookup"><span data-stu-id="eeb82-105">Members</span></span>  
  
|<span data-ttu-id="eeb82-106">成员</span><span class="sxs-lookup"><span data-stu-id="eeb82-106">Member</span></span>|<span data-ttu-id="eeb82-107">描述</span><span class="sxs-lookup"><span data-stu-id="eeb82-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="eeb82-108">缓存的 Windows 运行时类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="eeb82-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="eeb82-109">指向一个 ICorDebugType 对象，提供有关缓存类型的信息的指针。</span><span class="sxs-lookup"><span data-stu-id="eeb82-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eeb82-110">要求</span><span class="sxs-lookup"><span data-stu-id="eeb82-110">Requirements</span></span>  
 <span data-ttu-id="eeb82-111">**平台：** Windows 运行时。</span><span class="sxs-lookup"><span data-stu-id="eeb82-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="eeb82-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eeb82-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eeb82-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeb82-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeb82-114">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb82-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb82-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="eeb82-115">See also</span></span>

- [<span data-ttu-id="eeb82-116">调试结构</span><span class="sxs-lookup"><span data-stu-id="eeb82-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="eeb82-117">调试</span><span class="sxs-lookup"><span data-stu-id="eeb82-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
