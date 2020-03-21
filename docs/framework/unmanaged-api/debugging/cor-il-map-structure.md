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
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179296"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="7516d-102">COR_IL_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="7516d-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="7516d-103">指定函数的相对偏移量的更改。</span><span class="sxs-lookup"><span data-stu-id="7516d-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7516d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7516d-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="7516d-105">成员</span><span class="sxs-lookup"><span data-stu-id="7516d-105">Members</span></span>  
  
|<span data-ttu-id="7516d-106">成员</span><span class="sxs-lookup"><span data-stu-id="7516d-106">Member</span></span>|<span data-ttu-id="7516d-107">说明</span><span class="sxs-lookup"><span data-stu-id="7516d-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="7516d-108">旧的 Microsoft 中间语言 （MSIL） 相对于函数的开头偏移。</span><span class="sxs-lookup"><span data-stu-id="7516d-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="7516d-109">新的 MSIL 相对于函数的开头偏移。</span><span class="sxs-lookup"><span data-stu-id="7516d-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="7516d-110">`true`如果已知映射准确;如果映射准确;否则， `false`.</span><span class="sxs-lookup"><span data-stu-id="7516d-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7516d-111">备注</span><span class="sxs-lookup"><span data-stu-id="7516d-111">Remarks</span></span>  
 <span data-ttu-id="7516d-112">地图的格式如下：调试器将假定引用`oldOffset`原始未修改的 MSIL 代码中的 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="7516d-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="7516d-113">该`newOffset`参数是指新检测代码中的相应 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="7516d-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="7516d-114">为了正常工作，应满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="7516d-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="7516d-115">地图应按升序排序。</span><span class="sxs-lookup"><span data-stu-id="7516d-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="7516d-116">不应重新排序已检测的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="7516d-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="7516d-117">不应删除原始 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="7516d-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="7516d-118">地图应包括用于映射程序数据库 （PDB） 文件中的所有序列点的条目。</span><span class="sxs-lookup"><span data-stu-id="7516d-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="7516d-119">地图不会插值缺少的条目。</span><span class="sxs-lookup"><span data-stu-id="7516d-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="7516d-120">下面的示例显示地图及其结果。</span><span class="sxs-lookup"><span data-stu-id="7516d-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="7516d-121">Map:</span><span class="sxs-lookup"><span data-stu-id="7516d-121">Map:</span></span>  
  
- <span data-ttu-id="7516d-122">0 旧偏移，0 新偏移</span><span class="sxs-lookup"><span data-stu-id="7516d-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="7516d-123">5 个旧偏移，10 个新偏移</span><span class="sxs-lookup"><span data-stu-id="7516d-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="7516d-124">9 个旧偏移，20 个新偏移</span><span class="sxs-lookup"><span data-stu-id="7516d-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="7516d-125">结果：</span><span class="sxs-lookup"><span data-stu-id="7516d-125">Results:</span></span>  
  
- <span data-ttu-id="7516d-126">旧偏移 0、1、2、3 或 4 将映射到新的偏移量 0。</span><span class="sxs-lookup"><span data-stu-id="7516d-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="7516d-127">旧偏移 5、6、7 或 8 将映射到新的偏移量 10。</span><span class="sxs-lookup"><span data-stu-id="7516d-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="7516d-128">旧偏移量为 9 或更高，将映射到新的偏移量 20。</span><span class="sxs-lookup"><span data-stu-id="7516d-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="7516d-129">新的偏移量为 0、1、2、3、4、5、6、7、8 或 9 将映射到旧偏移 0。</span><span class="sxs-lookup"><span data-stu-id="7516d-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="7516d-130">10、11、12、13、14、15、16、17、18 或 19 的新偏移将映射到旧偏移 5。</span><span class="sxs-lookup"><span data-stu-id="7516d-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="7516d-131">新的偏移量为 20 或更高，将映射到旧偏移 9。</span><span class="sxs-lookup"><span data-stu-id="7516d-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7516d-132">要求</span><span class="sxs-lookup"><span data-stu-id="7516d-132">Requirements</span></span>  
 <span data-ttu-id="7516d-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7516d-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7516d-134">**标题：** 科尔科调试.idl， 科尔普罗芬.伊德尔</span><span class="sxs-lookup"><span data-stu-id="7516d-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="7516d-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7516d-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7516d-136">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7516d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7516d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7516d-137">See also</span></span>

- [<span data-ttu-id="7516d-138">调试结构</span><span class="sxs-lookup"><span data-stu-id="7516d-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="7516d-139">调试</span><span class="sxs-lookup"><span data-stu-id="7516d-139">Debugging</span></span>](index.md)
