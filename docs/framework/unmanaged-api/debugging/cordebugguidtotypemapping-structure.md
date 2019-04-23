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
ms.openlocfilehash: 9dc7093edaf12e801a1e1adc52b0be823ff92b91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079911"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="4cf60-102">CorDebugGuidToTypeMapping 结构</span><span class="sxs-lookup"><span data-stu-id="4cf60-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="4cf60-103">映射[!INCLUDE[wrt](../../../../includes/wrt-md.md)]GUID 传递给其相应的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="4cf60-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf60-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cf60-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="4cf60-105">成员</span><span class="sxs-lookup"><span data-stu-id="4cf60-105">Members</span></span>  
  
|<span data-ttu-id="4cf60-106">成员</span><span class="sxs-lookup"><span data-stu-id="4cf60-106">Member</span></span>|<span data-ttu-id="4cf60-107">描述</span><span class="sxs-lookup"><span data-stu-id="4cf60-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="4cf60-108">已缓存的 GUID[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="4cf60-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="4cf60-109">指向一个 ICorDebugType 对象，提供有关缓存类型的信息的指针。</span><span class="sxs-lookup"><span data-stu-id="4cf60-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cf60-110">要求</span><span class="sxs-lookup"><span data-stu-id="4cf60-110">Requirements</span></span>  
 <span data-ttu-id="4cf60-111">**平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4cf60-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="4cf60-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cf60-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cf60-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cf60-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cf60-114">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cf60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf60-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cf60-115">See also</span></span>

- [<span data-ttu-id="4cf60-116">调试结构</span><span class="sxs-lookup"><span data-stu-id="4cf60-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="4cf60-117">调试</span><span class="sxs-lookup"><span data-stu-id="4cf60-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
