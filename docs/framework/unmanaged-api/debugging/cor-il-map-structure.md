---
title: COR_IL_MAP 结构
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02a7bff021387f615c823b2df96615c1284cb82b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617713"
---
# <a name="corilmap-structure"></a><span data-ttu-id="697aa-102">COR_IL_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="697aa-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="697aa-103">指定函数的相对偏移量的更改。</span><span class="sxs-lookup"><span data-stu-id="697aa-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="697aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="697aa-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="697aa-105">成员</span><span class="sxs-lookup"><span data-stu-id="697aa-105">Members</span></span>  
  
|<span data-ttu-id="697aa-106">成员</span><span class="sxs-lookup"><span data-stu-id="697aa-106">Member</span></span>|<span data-ttu-id="697aa-107">描述</span><span class="sxs-lookup"><span data-stu-id="697aa-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="697aa-108">旧 Microsoft 中间语言 (MSIL) 偏移量相对于函数的开头。</span><span class="sxs-lookup"><span data-stu-id="697aa-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="697aa-109">相对于函数的开头新 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="697aa-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="697aa-110">`true` 如果映射已知的为准确起见;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="697aa-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="697aa-111">备注</span><span class="sxs-lookup"><span data-stu-id="697aa-111">Remarks</span></span>  
 <span data-ttu-id="697aa-112">映射的格式如下所示：调试器将假定`oldOffset`指的是原始的未修改 MSIL 代码中的 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="697aa-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="697aa-113">`newOffset`参数引用的新的已检测代码中的相应 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="697aa-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="697aa-114">单步执行才能正常工作，应满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="697aa-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="697aa-115">映射应按升序排序。</span><span class="sxs-lookup"><span data-stu-id="697aa-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="697aa-116">已检测的 MSIL 代码不应重新排序。</span><span class="sxs-lookup"><span data-stu-id="697aa-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="697aa-117">不应删除原始的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="697aa-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="697aa-118">映射应包含要映射的程序数据库 (PDB) 文件中的所有序列点的条目。</span><span class="sxs-lookup"><span data-stu-id="697aa-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="697aa-119">映射不会插入缺失的条目。</span><span class="sxs-lookup"><span data-stu-id="697aa-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="697aa-120">下面的示例显示了映射及其结果。</span><span class="sxs-lookup"><span data-stu-id="697aa-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="697aa-121">映射：</span><span class="sxs-lookup"><span data-stu-id="697aa-121">Map:</span></span>  
  
- <span data-ttu-id="697aa-122">旧偏移量为 0，0 新偏移量</span><span class="sxs-lookup"><span data-stu-id="697aa-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="697aa-123">旧偏移量为 5、 10 个新的偏移量</span><span class="sxs-lookup"><span data-stu-id="697aa-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="697aa-124">9 旧的偏移量，新偏移量为 20</span><span class="sxs-lookup"><span data-stu-id="697aa-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="697aa-125">结果：</span><span class="sxs-lookup"><span data-stu-id="697aa-125">Results:</span></span>  
  
- <span data-ttu-id="697aa-126">旧的偏移量为 0、 1、 2、 3 或 4 将映射到新偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="697aa-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="697aa-127">旧的偏移量为 5、 6、 7 或 8 将映射到新偏移量为 10。</span><span class="sxs-lookup"><span data-stu-id="697aa-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="697aa-128">旧的偏移量为 9 或更高版本将映射到新偏移量为 20。</span><span class="sxs-lookup"><span data-stu-id="697aa-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="697aa-129">新的偏移量为 0、 1、 2、 3、 4、 5、 6、 7、 8 或 9 将映射到旧偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="697aa-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="697aa-130">新的偏移 10、 11、 12、 13、 14、 15、 16、 17、 18 或 19 的将映射到旧偏移量为 5。</span><span class="sxs-lookup"><span data-stu-id="697aa-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="697aa-131">为 20 或更高版本的新偏移量将映射到旧偏移量为 9。</span><span class="sxs-lookup"><span data-stu-id="697aa-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="697aa-132">要求</span><span class="sxs-lookup"><span data-stu-id="697aa-132">Requirements</span></span>  
 <span data-ttu-id="697aa-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="697aa-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="697aa-134">**标头：** CorDebug.idl CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="697aa-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="697aa-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="697aa-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="697aa-136">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="697aa-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697aa-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="697aa-137">See also</span></span>

- [<span data-ttu-id="697aa-138">调试结构</span><span class="sxs-lookup"><span data-stu-id="697aa-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="697aa-139">调试</span><span class="sxs-lookup"><span data-stu-id="697aa-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
