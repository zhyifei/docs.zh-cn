---
title: CorDebugGenerationTypes 枚举
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1707a09f14fbab6150c2ecbcd188d7bf88064fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085891"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="a7fdd-102">CorDebugGenerationTypes 枚举</span><span class="sxs-lookup"><span data-stu-id="a7fdd-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="a7fdd-103">指定托管堆上内存区域的生成。</span><span class="sxs-lookup"><span data-stu-id="a7fdd-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7fdd-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7fdd-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="a7fdd-105">成员</span><span class="sxs-lookup"><span data-stu-id="a7fdd-105">Members</span></span>  
  
|<span data-ttu-id="a7fdd-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="a7fdd-106">Member name</span></span>|<span data-ttu-id="a7fdd-107">描述</span><span class="sxs-lookup"><span data-stu-id="a7fdd-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="a7fdd-108">第 0 代。</span><span class="sxs-lookup"><span data-stu-id="a7fdd-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="a7fdd-109">第 1 代。</span><span class="sxs-lookup"><span data-stu-id="a7fdd-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="a7fdd-110">第 2 代。</span><span class="sxs-lookup"><span data-stu-id="a7fdd-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="a7fdd-111">大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="a7fdd-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7fdd-112">备注</span><span class="sxs-lookup"><span data-stu-id="a7fdd-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7fdd-113">要求</span><span class="sxs-lookup"><span data-stu-id="a7fdd-113">Requirements</span></span>  
 <span data-ttu-id="a7fdd-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7fdd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7fdd-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7fdd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7fdd-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7fdd-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a7fdd-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a7fdd-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7fdd-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7fdd-118">See also</span></span>

- [<span data-ttu-id="a7fdd-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="a7fdd-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
