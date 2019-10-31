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
ms.openlocfilehash: 313f6649448653ad630d616c7dbf739653e352dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132837"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="bd6bd-102">CorDebugGuidToTypeMapping 结构</span><span class="sxs-lookup"><span data-stu-id="bd6bd-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="bd6bd-103">将 Windows 运行时 GUID 映射到其对应的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="bd6bd-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd6bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd6bd-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="bd6bd-105">Members</span><span class="sxs-lookup"><span data-stu-id="bd6bd-105">Members</span></span>  
  
|<span data-ttu-id="bd6bd-106">成员</span><span class="sxs-lookup"><span data-stu-id="bd6bd-106">Member</span></span>|<span data-ttu-id="bd6bd-107">描述</span><span class="sxs-lookup"><span data-stu-id="bd6bd-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="bd6bd-108">缓存的 Windows 运行时类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="bd6bd-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="bd6bd-109">指向 ICorDebugType 对象的指针，该对象提供有关缓存类型的信息。</span><span class="sxs-lookup"><span data-stu-id="bd6bd-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd6bd-110">要求</span><span class="sxs-lookup"><span data-stu-id="bd6bd-110">Requirements</span></span>  
 <span data-ttu-id="bd6bd-111">**平台：** Windows 运行时。</span><span class="sxs-lookup"><span data-stu-id="bd6bd-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="bd6bd-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd6bd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd6bd-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd6bd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd6bd-114">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd6bd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd6bd-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd6bd-115">See also</span></span>

- [<span data-ttu-id="bd6bd-116">调试结构</span><span class="sxs-lookup"><span data-stu-id="bd6bd-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="bd6bd-117">调试</span><span class="sxs-lookup"><span data-stu-id="bd6bd-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
