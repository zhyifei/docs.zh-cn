---
title: "CorDebugGuidToTypeMapping 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugGuidToTypeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGuidToTypeMapping
helpviewer_keywords: CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4c829f4a74c3d2e84a070dfbe5d35d89b1b7ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="9a8f0-102">CorDebugGuidToTypeMapping 结构</span><span class="sxs-lookup"><span data-stu-id="9a8f0-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="9a8f0-103">地图[!INCLUDE[wrt](../../../../includes/wrt-md.md)]到其相应的 ICorDebugType 对象的 GUID。</span><span class="sxs-lookup"><span data-stu-id="9a8f0-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a8f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="9a8f0-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="9a8f0-105">成员</span><span class="sxs-lookup"><span data-stu-id="9a8f0-105">Members</span></span>  
  
|<span data-ttu-id="9a8f0-106">成员</span><span class="sxs-lookup"><span data-stu-id="9a8f0-106">Member</span></span>|<span data-ttu-id="9a8f0-107">描述</span><span class="sxs-lookup"><span data-stu-id="9a8f0-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="9a8f0-108">已缓存的 GUID[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="9a8f0-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="9a8f0-109">指向一个 ICorDebugType 对象，提供有关缓存类型的信息的指针。</span><span class="sxs-lookup"><span data-stu-id="9a8f0-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a8f0-110">要求</span><span class="sxs-lookup"><span data-stu-id="9a8f0-110">Requirements</span></span>  
 <span data-ttu-id="9a8f0-111">**平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9a8f0-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="9a8f0-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a8f0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a8f0-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a8f0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a8f0-114">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8f0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8f0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a8f0-115">See Also</span></span>  
 [<span data-ttu-id="9a8f0-116">调试结构</span><span class="sxs-lookup"><span data-stu-id="9a8f0-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="9a8f0-117">调试</span><span class="sxs-lookup"><span data-stu-id="9a8f0-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
