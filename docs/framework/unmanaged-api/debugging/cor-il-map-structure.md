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
ms.openlocfilehash: c7452b76509d5eca592cc3b95df1f77703ec1111
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561824"
---
# <a name="corilmap-structure"></a><span data-ttu-id="26c1d-102">COR_IL_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="26c1d-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="26c1d-103">指定函数的相对偏移量的更改。</span><span class="sxs-lookup"><span data-stu-id="26c1d-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="26c1d-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="26c1d-105">成员</span><span class="sxs-lookup"><span data-stu-id="26c1d-105">Members</span></span>  
  
|<span data-ttu-id="26c1d-106">成员</span><span class="sxs-lookup"><span data-stu-id="26c1d-106">Member</span></span>|<span data-ttu-id="26c1d-107">描述</span><span class="sxs-lookup"><span data-stu-id="26c1d-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="26c1d-108">旧 Microsoft 中间语言 (MSIL) 偏移量相对于函数的开头。</span><span class="sxs-lookup"><span data-stu-id="26c1d-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="26c1d-109">相对于函数的开头新 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="26c1d-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="26c1d-110">`true` 如果映射已知的为准确起见;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="26c1d-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26c1d-111">备注</span><span class="sxs-lookup"><span data-stu-id="26c1d-111">Remarks</span></span>  
 <span data-ttu-id="26c1d-112">映射的格式如下所示：调试器将假定`oldOffset`指的是原始的未修改 MSIL 代码中的 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="26c1d-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="26c1d-113">`newOffset`参数引用的新的已检测代码中的相应 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="26c1d-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="26c1d-114">单步执行才能正常工作，应满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="26c1d-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
-   <span data-ttu-id="26c1d-115">映射应按升序排序。</span><span class="sxs-lookup"><span data-stu-id="26c1d-115">The map should be sorted in ascending order.</span></span>  
  
-   <span data-ttu-id="26c1d-116">已检测的 MSIL 代码不应重新排序。</span><span class="sxs-lookup"><span data-stu-id="26c1d-116">Instrumented MSIL code should not be reordered.</span></span>  
  
-   <span data-ttu-id="26c1d-117">不应删除原始的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="26c1d-117">Original MSIL code should not be removed.</span></span>  
  
-   <span data-ttu-id="26c1d-118">映射应包含要映射的程序数据库 (PDB) 文件中的所有序列点的条目。</span><span class="sxs-lookup"><span data-stu-id="26c1d-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="26c1d-119">映射不会插入缺失的条目。</span><span class="sxs-lookup"><span data-stu-id="26c1d-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="26c1d-120">下面的示例显示了映射及其结果。</span><span class="sxs-lookup"><span data-stu-id="26c1d-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="26c1d-121">映射：</span><span class="sxs-lookup"><span data-stu-id="26c1d-121">Map:</span></span>  
  
-   <span data-ttu-id="26c1d-122">旧偏移量为 0，0 新偏移量</span><span class="sxs-lookup"><span data-stu-id="26c1d-122">0 old offset, 0 new offset</span></span>  
  
-   <span data-ttu-id="26c1d-123">旧偏移量为 5、 10 个新的偏移量</span><span class="sxs-lookup"><span data-stu-id="26c1d-123">5 old offset, 10 new offset</span></span>  
  
-   <span data-ttu-id="26c1d-124">9 旧的偏移量，新偏移量为 20</span><span class="sxs-lookup"><span data-stu-id="26c1d-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="26c1d-125">结果：</span><span class="sxs-lookup"><span data-stu-id="26c1d-125">Results:</span></span>  
  
-   <span data-ttu-id="26c1d-126">旧的偏移量为 0、 1、 2、 3 或 4 将映射到新偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="26c1d-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
-   <span data-ttu-id="26c1d-127">旧的偏移量为 5、 6、 7 或 8 将映射到新偏移量为 10。</span><span class="sxs-lookup"><span data-stu-id="26c1d-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
-   <span data-ttu-id="26c1d-128">旧的偏移量为 9 或更高版本将映射到新偏移量为 20。</span><span class="sxs-lookup"><span data-stu-id="26c1d-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
-   <span data-ttu-id="26c1d-129">新的偏移量为 0、 1、 2、 3、 4、 5、 6、 7、 8 或 9 将映射到旧偏移量为 0。</span><span class="sxs-lookup"><span data-stu-id="26c1d-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
-   <span data-ttu-id="26c1d-130">新的偏移 10、 11、 12、 13、 14、 15、 16、 17、 18 或 19 的将映射到旧偏移量为 5。</span><span class="sxs-lookup"><span data-stu-id="26c1d-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
-   <span data-ttu-id="26c1d-131">为 20 或更高版本的新偏移量将映射到旧偏移量为 9。</span><span class="sxs-lookup"><span data-stu-id="26c1d-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26c1d-132">要求</span><span class="sxs-lookup"><span data-stu-id="26c1d-132">Requirements</span></span>  
 <span data-ttu-id="26c1d-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26c1d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26c1d-134">**标头：** CorDebug.idl CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="26c1d-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="26c1d-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26c1d-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26c1d-136">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26c1d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c1d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="26c1d-137">See also</span></span>
- [<span data-ttu-id="26c1d-138">调试结构</span><span class="sxs-lookup"><span data-stu-id="26c1d-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="26c1d-139">调试</span><span class="sxs-lookup"><span data-stu-id="26c1d-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
