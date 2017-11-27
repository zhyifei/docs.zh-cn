---
title: "CorDebugGenerationTypes 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugGenerationTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGenerationTypes
helpviewer_keywords: CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: adefc0de4ba09419660c214df75365c90ec2c66e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="3b5ba-102">CorDebugGenerationTypes 枚举</span><span class="sxs-lookup"><span data-stu-id="3b5ba-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="3b5ba-103">指定托管堆上内存区域的生成。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b5ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b5ba-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="3b5ba-105">成员</span><span class="sxs-lookup"><span data-stu-id="3b5ba-105">Members</span></span>  
  
|<span data-ttu-id="3b5ba-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="3b5ba-106">Member name</span></span>|<span data-ttu-id="3b5ba-107">描述</span><span class="sxs-lookup"><span data-stu-id="3b5ba-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="3b5ba-108">第 0 代。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="3b5ba-109">第 1 代。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="3b5ba-110">第 2 代。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="3b5ba-111">大型对象堆中。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b5ba-112">备注</span><span class="sxs-lookup"><span data-stu-id="3b5ba-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b5ba-113">要求</span><span class="sxs-lookup"><span data-stu-id="3b5ba-113">Requirements</span></span>  
 <span data-ttu-id="3b5ba-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b5ba-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b5ba-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b5ba-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b5ba-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b5ba-117">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b5ba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b5ba-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b5ba-118">See Also</span></span>  
 [<span data-ttu-id="3b5ba-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="3b5ba-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
