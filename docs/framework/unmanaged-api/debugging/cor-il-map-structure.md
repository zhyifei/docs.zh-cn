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
ms.openlocfilehash: 5ae4c5743b01c4a9087323678d315473631cb32f
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274042"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="b97dd-102">COR_IL_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="b97dd-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="b97dd-103">指定函数的相对偏移量的更改。</span><span class="sxs-lookup"><span data-stu-id="b97dd-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b97dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="b97dd-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="b97dd-105">成员</span><span class="sxs-lookup"><span data-stu-id="b97dd-105">Members</span></span>  
  
|<span data-ttu-id="b97dd-106">成员</span><span class="sxs-lookup"><span data-stu-id="b97dd-106">Member</span></span>|<span data-ttu-id="b97dd-107">描述</span><span class="sxs-lookup"><span data-stu-id="b97dd-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="b97dd-108">相对于函数开头的旧 Microsoft 中间语言（MSIL）偏移量。</span><span class="sxs-lookup"><span data-stu-id="b97dd-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="b97dd-109">相对于函数开头的新 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="b97dd-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="b97dd-110">`true`如果已知正确的映射，则为;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b97dd-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b97dd-111">备注</span><span class="sxs-lookup"><span data-stu-id="b97dd-111">Remarks</span></span>  
 <span data-ttu-id="b97dd-112">图的格式如下所示：调试器将假设`oldOffset`是在原始的、未修改的 msil 代码内引用 msil 偏移量。</span><span class="sxs-lookup"><span data-stu-id="b97dd-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="b97dd-113">`newOffset`参数引用新的、经过检测的代码中的相应 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="b97dd-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="b97dd-114">若要单步执行，应满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="b97dd-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="b97dd-115">地图应按升序排序。</span><span class="sxs-lookup"><span data-stu-id="b97dd-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="b97dd-116">不应对已检测的 MSIL 代码进行重新排序。</span><span class="sxs-lookup"><span data-stu-id="b97dd-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="b97dd-117">不应删除原始的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="b97dd-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="b97dd-118">映射应包括用于映射程序数据库（PDB）文件中的所有序列点的条目。</span><span class="sxs-lookup"><span data-stu-id="b97dd-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="b97dd-119">地图未插入缺失的条目。</span><span class="sxs-lookup"><span data-stu-id="b97dd-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="b97dd-120">下面的示例演示了一个映射及其结果。</span><span class="sxs-lookup"><span data-stu-id="b97dd-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="b97dd-121">将</span><span class="sxs-lookup"><span data-stu-id="b97dd-121">Map:</span></span>  
  
- <span data-ttu-id="b97dd-122">0个旧偏移，0个新偏移</span><span class="sxs-lookup"><span data-stu-id="b97dd-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="b97dd-123">5旧偏移量，10个新偏移</span><span class="sxs-lookup"><span data-stu-id="b97dd-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="b97dd-124">9旧偏移，20个新偏移</span><span class="sxs-lookup"><span data-stu-id="b97dd-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="b97dd-125">后果</span><span class="sxs-lookup"><span data-stu-id="b97dd-125">Results:</span></span>  
  
- <span data-ttu-id="b97dd-126">早于0、1、2、3或4的偏移将映射到新的偏移量0。</span><span class="sxs-lookup"><span data-stu-id="b97dd-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="b97dd-127">旧偏移量5、6、7或8将映射到新的偏移量10。</span><span class="sxs-lookup"><span data-stu-id="b97dd-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="b97dd-128">旧偏移量9或更高将映射到新偏移量20。</span><span class="sxs-lookup"><span data-stu-id="b97dd-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="b97dd-129">新偏移量为0、1、2、3、4、5、6、7、8或9，将映射到旧偏移量0。</span><span class="sxs-lookup"><span data-stu-id="b97dd-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="b97dd-130">新偏移量为10、11、12、13、14、15、16、17、18或19，将映射到旧偏移量5。</span><span class="sxs-lookup"><span data-stu-id="b97dd-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="b97dd-131">20或更高的新偏移量将映射到旧偏移量9。</span><span class="sxs-lookup"><span data-stu-id="b97dd-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b97dd-132">要求</span><span class="sxs-lookup"><span data-stu-id="b97dd-132">Requirements</span></span>  
 <span data-ttu-id="b97dd-133">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b97dd-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b97dd-134">**标头：** Cordebug.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="b97dd-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="b97dd-135">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b97dd-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b97dd-136">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b97dd-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97dd-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b97dd-137">See also</span></span>

- [<span data-ttu-id="b97dd-138">调试结构</span><span class="sxs-lookup"><span data-stu-id="b97dd-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b97dd-139">调试</span><span class="sxs-lookup"><span data-stu-id="b97dd-139">Debugging</span></span>](index.md)
