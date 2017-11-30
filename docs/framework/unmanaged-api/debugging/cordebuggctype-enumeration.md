---
title: "CorDebugGCType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugGCType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGCType
helpviewer_keywords: CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 14d6f28c2e5fa356c7f406ffb4c2787f0ace500a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="e8910-102">CorDebugGCType 枚举</span><span class="sxs-lookup"><span data-stu-id="e8910-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="e8910-103">指示垃圾回收器是在工作站还是服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="e8910-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8910-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8910-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8910-105">参数</span><span class="sxs-lookup"><span data-stu-id="e8910-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="e8910-106">成员</span><span class="sxs-lookup"><span data-stu-id="e8910-106">Members</span></span>  
  
|<span data-ttu-id="e8910-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="e8910-107">Member name</span></span>|<span data-ttu-id="e8910-108">描述</span><span class="sxs-lookup"><span data-stu-id="e8910-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="e8910-109">在工作站上运行垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="e8910-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="e8910-110">在服务器上运行垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="e8910-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8910-111">备注</span><span class="sxs-lookup"><span data-stu-id="e8910-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8910-112">要求</span><span class="sxs-lookup"><span data-stu-id="e8910-112">Requirements</span></span>  
 <span data-ttu-id="e8910-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8910-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8910-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8910-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8910-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8910-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8910-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8910-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8910-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8910-117">See Also</span></span>  
 [<span data-ttu-id="e8910-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="e8910-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
