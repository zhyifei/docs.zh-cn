---
title: COR_PUB_ENUMPROCESS 枚举
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcdb5883e109d7e0c73c8fb76ee61b52cf23091f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406996"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="413f9-102">COR_PUB_ENUMPROCESS 枚举</span><span class="sxs-lookup"><span data-stu-id="413f9-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="413f9-103">标识要枚举的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="413f9-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="413f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="413f9-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="413f9-105">成员</span><span class="sxs-lookup"><span data-stu-id="413f9-105">Members</span></span>  
  
|<span data-ttu-id="413f9-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="413f9-106">Member name</span></span>|<span data-ttu-id="413f9-107">描述</span><span class="sxs-lookup"><span data-stu-id="413f9-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="413f9-108">托管的进程。</span><span class="sxs-lookup"><span data-stu-id="413f9-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="413f9-109">备注</span><span class="sxs-lookup"><span data-stu-id="413f9-109">Remarks</span></span>  
 <span data-ttu-id="413f9-110">非托管调试 API 的当前版本仅枚举托管进程。</span><span class="sxs-lookup"><span data-stu-id="413f9-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="413f9-111">要求</span><span class="sxs-lookup"><span data-stu-id="413f9-111">Requirements</span></span>  
 <span data-ttu-id="413f9-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="413f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="413f9-113">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="413f9-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="413f9-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="413f9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="413f9-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="413f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="413f9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="413f9-116">See Also</span></span>  
 [<span data-ttu-id="413f9-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="413f9-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
