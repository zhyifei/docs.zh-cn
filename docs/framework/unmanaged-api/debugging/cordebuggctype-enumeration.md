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
ms.openlocfilehash: 6f4c96517375df4cd249b72953bf37812a498c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789360"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="bb5c4-102">CorDebugGCType 枚举</span><span class="sxs-lookup"><span data-stu-id="bb5c4-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="bb5c4-103">指示垃圾回收器是在工作站还是服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="bb5c4-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb5c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb5c4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb5c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb5c4-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="bb5c4-106">Members</span><span class="sxs-lookup"><span data-stu-id="bb5c4-106">Members</span></span>  
  
|<span data-ttu-id="bb5c4-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="bb5c4-107">Member name</span></span>|<span data-ttu-id="bb5c4-108">描述</span><span class="sxs-lookup"><span data-stu-id="bb5c4-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="bb5c4-109">垃圾回收器正在工作站上运行。</span><span class="sxs-lookup"><span data-stu-id="bb5c4-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="bb5c4-110">垃圾回收器正在服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="bb5c4-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb5c4-111">备注</span><span class="sxs-lookup"><span data-stu-id="bb5c4-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb5c4-112">需求</span><span class="sxs-lookup"><span data-stu-id="bb5c4-112">Requirements</span></span>  
 <span data-ttu-id="bb5c4-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5c4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb5c4-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb5c4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb5c4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb5c4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb5c4-116">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb5c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5c4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb5c4-117">See also</span></span>

- [<span data-ttu-id="bb5c4-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="bb5c4-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
