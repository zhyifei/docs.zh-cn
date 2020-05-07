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
ms.openlocfilehash: 0443f58b79e60111756308cc4843daf86d1fc823
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795860"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="90eac-102">CorDebugGenerationTypes 枚举</span><span class="sxs-lookup"><span data-stu-id="90eac-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="90eac-103">指定托管堆上内存区域的生成。</span><span class="sxs-lookup"><span data-stu-id="90eac-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90eac-104">语法</span><span class="sxs-lookup"><span data-stu-id="90eac-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="90eac-105">成员</span><span class="sxs-lookup"><span data-stu-id="90eac-105">Members</span></span>  
  
|<span data-ttu-id="90eac-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="90eac-106">Member name</span></span>|<span data-ttu-id="90eac-107">说明</span><span class="sxs-lookup"><span data-stu-id="90eac-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="90eac-108">第 0 代。</span><span class="sxs-lookup"><span data-stu-id="90eac-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="90eac-109">第 1 代。</span><span class="sxs-lookup"><span data-stu-id="90eac-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="90eac-110">第 2 代。</span><span class="sxs-lookup"><span data-stu-id="90eac-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="90eac-111">大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="90eac-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90eac-112">备注</span><span class="sxs-lookup"><span data-stu-id="90eac-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90eac-113">要求</span><span class="sxs-lookup"><span data-stu-id="90eac-113">Requirements</span></span>  
 <span data-ttu-id="90eac-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90eac-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90eac-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90eac-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90eac-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90eac-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90eac-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90eac-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90eac-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90eac-118">See also</span></span>

- [<span data-ttu-id="90eac-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="90eac-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
