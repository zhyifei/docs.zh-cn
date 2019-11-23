---
title: COR_PRF_FUNCTION 结构
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
ms.openlocfilehash: 40698a49ac7012c4f67eb88b1ead04c80f3dea77
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428327"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="3a205-102">COR_PRF_FUNCTION 结构</span><span class="sxs-lookup"><span data-stu-id="3a205-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="3a205-103">通过将函数的 ID 与其重新编译的 ID 版本组合起来，提供该函数的唯一表示形式。</span><span class="sxs-lookup"><span data-stu-id="3a205-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a205-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a205-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="3a205-105">Members</span><span class="sxs-lookup"><span data-stu-id="3a205-105">Members</span></span>  
  
|<span data-ttu-id="3a205-106">成员</span><span class="sxs-lookup"><span data-stu-id="3a205-106">Member</span></span>|<span data-ttu-id="3a205-107">描述</span><span class="sxs-lookup"><span data-stu-id="3a205-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="3a205-108">The ID of the function.</span><span class="sxs-lookup"><span data-stu-id="3a205-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="3a205-109">The ID of the recompiled function.</span><span class="sxs-lookup"><span data-stu-id="3a205-109">The ID of the recompiled function.</span></span> <span data-ttu-id="3a205-110">A value of 0 (zero) represents the original version of the function.</span><span class="sxs-lookup"><span data-stu-id="3a205-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a205-111">备注</span><span class="sxs-lookup"><span data-stu-id="3a205-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a205-112">要求</span><span class="sxs-lookup"><span data-stu-id="3a205-112">Requirements</span></span>  
 <span data-ttu-id="3a205-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a205-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a205-114">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="3a205-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3a205-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a205-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a205-116">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a205-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a205-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a205-117">See also</span></span>

- [<span data-ttu-id="3a205-118">分析结构</span><span class="sxs-lookup"><span data-stu-id="3a205-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
