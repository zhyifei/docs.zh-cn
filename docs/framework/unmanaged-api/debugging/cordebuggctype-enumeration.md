---
title: CorDebugGCType 枚举
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
ms.openlocfilehash: 8dd070d2c895a94ac996be81e672bd67f59b83b7
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795893"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="d0bdd-102">CorDebugGCType 枚举</span><span class="sxs-lookup"><span data-stu-id="d0bdd-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="d0bdd-103">指示垃圾回收器是在工作站还是服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="d0bdd-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0bdd-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0bdd-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0bdd-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0bdd-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="d0bdd-106">成员</span><span class="sxs-lookup"><span data-stu-id="d0bdd-106">Members</span></span>  
  
|<span data-ttu-id="d0bdd-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="d0bdd-107">Member name</span></span>|<span data-ttu-id="d0bdd-108">说明</span><span class="sxs-lookup"><span data-stu-id="d0bdd-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="d0bdd-109">垃圾回收器正在工作站上运行。</span><span class="sxs-lookup"><span data-stu-id="d0bdd-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="d0bdd-110">垃圾回收器正在服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="d0bdd-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0bdd-111">备注</span><span class="sxs-lookup"><span data-stu-id="d0bdd-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0bdd-112">要求</span><span class="sxs-lookup"><span data-stu-id="d0bdd-112">Requirements</span></span>  
 <span data-ttu-id="d0bdd-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bdd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0bdd-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0bdd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0bdd-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0bdd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0bdd-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0bdd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bdd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0bdd-117">See also</span></span>

- [<span data-ttu-id="d0bdd-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="d0bdd-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
