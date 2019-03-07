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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe8be6a7c18fff54825f981672f0f640bb60c35c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482205"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="3125c-102">CorDebugGCType 枚举</span><span class="sxs-lookup"><span data-stu-id="3125c-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="3125c-103">指示垃圾回收器是在工作站还是服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="3125c-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3125c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3125c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3125c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3125c-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="3125c-106">成员</span><span class="sxs-lookup"><span data-stu-id="3125c-106">Members</span></span>  
  
|<span data-ttu-id="3125c-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="3125c-107">Member name</span></span>|<span data-ttu-id="3125c-108">描述</span><span class="sxs-lookup"><span data-stu-id="3125c-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="3125c-109">垃圾回收器运行在工作站上。</span><span class="sxs-lookup"><span data-stu-id="3125c-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="3125c-110">垃圾回收器服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="3125c-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3125c-111">备注</span><span class="sxs-lookup"><span data-stu-id="3125c-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3125c-112">要求</span><span class="sxs-lookup"><span data-stu-id="3125c-112">Requirements</span></span>  
 <span data-ttu-id="3125c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3125c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3125c-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3125c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3125c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3125c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3125c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3125c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3125c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3125c-117">See also</span></span>
- [<span data-ttu-id="3125c-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="3125c-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
