---
title: "CorDebugGCType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2045c2edd129c2e4154d24b43d96f6ea8ad64cab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="8f768-102">CorDebugGCType 枚举</span><span class="sxs-lookup"><span data-stu-id="8f768-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="8f768-103">指示垃圾回收器是在工作站还是服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="8f768-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f768-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f768-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f768-105">参数</span><span class="sxs-lookup"><span data-stu-id="8f768-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="8f768-106">成员</span><span class="sxs-lookup"><span data-stu-id="8f768-106">Members</span></span>  
  
|<span data-ttu-id="8f768-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="8f768-107">Member name</span></span>|<span data-ttu-id="8f768-108">描述</span><span class="sxs-lookup"><span data-stu-id="8f768-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="8f768-109">在工作站上运行垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="8f768-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="8f768-110">在服务器上运行垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="8f768-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f768-111">备注</span><span class="sxs-lookup"><span data-stu-id="8f768-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f768-112">惠?</span><span class="sxs-lookup"><span data-stu-id="8f768-112">Requirements</span></span>  
 <span data-ttu-id="8f768-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f768-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f768-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f768-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f768-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f768-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f768-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f768-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f768-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f768-117">See Also</span></span>  
 [<span data-ttu-id="8f768-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="8f768-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
