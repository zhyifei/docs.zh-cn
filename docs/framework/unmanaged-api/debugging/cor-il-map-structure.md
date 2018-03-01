---
title: "COR_IL_MAP 结构"
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
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e2772833d75ced2209896ca37cf6cf37fb965f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corilmap-structure"></a><span data-ttu-id="9db01-102">COR_IL_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="9db01-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="9db01-103">指定函数的相对偏移量的更改。</span><span class="sxs-lookup"><span data-stu-id="9db01-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db01-104">语法</span><span class="sxs-lookup"><span data-stu-id="9db01-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="9db01-105">成员</span><span class="sxs-lookup"><span data-stu-id="9db01-105">Members</span></span>  
  
|<span data-ttu-id="9db01-106">成员</span><span class="sxs-lookup"><span data-stu-id="9db01-106">Member</span></span>|<span data-ttu-id="9db01-107">描述</span><span class="sxs-lookup"><span data-stu-id="9db01-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="9db01-108">旧 Microsoft 中间语言 (MSIL) 偏移量相对于函数的开头。</span><span class="sxs-lookup"><span data-stu-id="9db01-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="9db01-109">相对于函数的开头新 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="9db01-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="9db01-110">`true`如果映射已知不准确的。否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="9db01-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9db01-111">备注</span><span class="sxs-lookup"><span data-stu-id="9db01-111">Remarks</span></span>  
 <span data-ttu-id="9db01-112">映射的格式如下： 调试器将假定`oldOffset`指内原始、 未修改 MSIL 代码的 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="9db01-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="9db01-113">`newOffset`参数是指已插入检测点的最新的代码中的相应 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="9db01-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="9db01-114">单步执行正常工作，应满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="9db01-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
-   <span data-ttu-id="9db01-115">应以升序排序映射。</span><span class="sxs-lookup"><span data-stu-id="9db01-115">The map should be sorted in ascending order.</span></span>  
  
-   <span data-ttu-id="9db01-116">已检测的 MSIL 代码不应重新排序。</span><span class="sxs-lookup"><span data-stu-id="9db01-116">Instrumented MSIL code should not be reordered.</span></span>  
  
-   <span data-ttu-id="9db01-117">不应删除原始的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="9db01-117">Original MSIL code should not be removed.</span></span>  
  
-   <span data-ttu-id="9db01-118">映射应包括要映射的程序数据库 (PDB) 文件中的所有序列点的条目。</span><span class="sxs-lookup"><span data-stu-id="9db01-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="9db01-119">映射不插入缺失的条目。</span><span class="sxs-lookup"><span data-stu-id="9db01-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="9db01-120">下面的示例显示地图和其结果。</span><span class="sxs-lookup"><span data-stu-id="9db01-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="9db01-121">映射：</span><span class="sxs-lookup"><span data-stu-id="9db01-121">Map:</span></span>  
  
-   <span data-ttu-id="9db01-122">旧偏移量为 0，0 新的偏移量</span><span class="sxs-lookup"><span data-stu-id="9db01-122">0 old offset, 0 new offset</span></span>  
  
-   <span data-ttu-id="9db01-123">旧偏移量为 5，10 个新的偏移量</span><span class="sxs-lookup"><span data-stu-id="9db01-123">5 old offset, 10 new offset</span></span>  
  
-   <span data-ttu-id="9db01-124">9 旧的偏移量，新偏移量为 20</span><span class="sxs-lookup"><span data-stu-id="9db01-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="9db01-125">结果：</span><span class="sxs-lookup"><span data-stu-id="9db01-125">Results:</span></span>  
  
-   <span data-ttu-id="9db01-126">旧偏移量为 0、 1、 2、 3 或 4 将映射到新的偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="9db01-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
-   <span data-ttu-id="9db01-127">旧偏移量为 5、 6、 7 或 8 将映射到新偏移量为 10。</span><span class="sxs-lookup"><span data-stu-id="9db01-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
-   <span data-ttu-id="9db01-128">旧偏移量 9 或更高版本将映射到新偏移量为 20。</span><span class="sxs-lookup"><span data-stu-id="9db01-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
-   <span data-ttu-id="9db01-129">新偏移量 0、 1、 2、 3、 4、 5、 6、 7、 8 或 9 将映射到旧偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="9db01-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
-   <span data-ttu-id="9db01-130">10、 11、 12、 13、 14、 15、 16、 17、 18 或 19 的新的偏移量将映射到旧偏移量为 5。</span><span class="sxs-lookup"><span data-stu-id="9db01-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
-   <span data-ttu-id="9db01-131">20 或更高版本的新的偏移量将映射到旧偏移量为 9。</span><span class="sxs-lookup"><span data-stu-id="9db01-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9db01-132">惠?</span><span class="sxs-lookup"><span data-stu-id="9db01-132">Requirements</span></span>  
 <span data-ttu-id="9db01-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9db01-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9db01-134">**标头：** CorDebug.idl、 CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9db01-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="9db01-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9db01-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9db01-136">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9db01-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db01-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="9db01-137">See Also</span></span>  
 [<span data-ttu-id="9db01-138">调试结构</span><span class="sxs-lookup"><span data-stu-id="9db01-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="9db01-139">调试</span><span class="sxs-lookup"><span data-stu-id="9db01-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
