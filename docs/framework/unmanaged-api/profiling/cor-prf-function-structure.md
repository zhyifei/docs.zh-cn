---
title: "COR_PRF_FUNCTION 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION
helpviewer_keywords: COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4b8ca316814b6f4df8792d068bea36d499b77374
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunction-structure"></a><span data-ttu-id="62331-102">COR_PRF_FUNCTION 结构</span><span class="sxs-lookup"><span data-stu-id="62331-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="62331-103">通过将函数的 ID 与其重新编译的 ID 版本组合起来，提供该函数的唯一表示形式。</span><span class="sxs-lookup"><span data-stu-id="62331-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62331-104">语法</span><span class="sxs-lookup"><span data-stu-id="62331-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="62331-105">成员</span><span class="sxs-lookup"><span data-stu-id="62331-105">Members</span></span>  
  
|<span data-ttu-id="62331-106">成员</span><span class="sxs-lookup"><span data-stu-id="62331-106">Member</span></span>|<span data-ttu-id="62331-107">描述</span><span class="sxs-lookup"><span data-stu-id="62331-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="62331-108">函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="62331-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="62331-109">重新编译函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="62331-109">The ID of the recompiled function.</span></span> <span data-ttu-id="62331-110">值为 0 （零） 表示函数的原始版本。</span><span class="sxs-lookup"><span data-stu-id="62331-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62331-111">备注</span><span class="sxs-lookup"><span data-stu-id="62331-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62331-112">要求</span><span class="sxs-lookup"><span data-stu-id="62331-112">Requirements</span></span>  
 <span data-ttu-id="62331-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62331-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62331-114">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="62331-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="62331-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62331-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62331-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62331-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62331-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62331-117">See Also</span></span>  
 [<span data-ttu-id="62331-118">分析结构</span><span class="sxs-lookup"><span data-stu-id="62331-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
