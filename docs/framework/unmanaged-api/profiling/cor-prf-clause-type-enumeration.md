---
title: COR_PRF_CLAUSE_TYPE 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 861f4c18f4c5151dc7215d300775928b88f018aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090623"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="53c84-102">COR_PRF_CLAUSE_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="53c84-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="53c84-103">指示代码刚进入或离开的异常子句的类型。</span><span class="sxs-lookup"><span data-stu-id="53c84-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c84-104">语法</span><span class="sxs-lookup"><span data-stu-id="53c84-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="53c84-105">成员</span><span class="sxs-lookup"><span data-stu-id="53c84-105">Members</span></span>  
  
|<span data-ttu-id="53c84-106">成员</span><span class="sxs-lookup"><span data-stu-id="53c84-106">Member</span></span>|<span data-ttu-id="53c84-107">描述</span><span class="sxs-lookup"><span data-stu-id="53c84-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="53c84-108">在异常子句无效。</span><span class="sxs-lookup"><span data-stu-id="53c84-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="53c84-109">在异常子句是筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="53c84-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="53c84-110">在异常子句是`catch`语句。</span><span class="sxs-lookup"><span data-stu-id="53c84-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="53c84-111">在异常子句是`finally`语句。</span><span class="sxs-lookup"><span data-stu-id="53c84-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53c84-112">要求</span><span class="sxs-lookup"><span data-stu-id="53c84-112">Requirements</span></span>  
 <span data-ttu-id="53c84-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53c84-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53c84-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53c84-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53c84-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53c84-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53c84-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53c84-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c84-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="53c84-117">See also</span></span>

- [<span data-ttu-id="53c84-118">分析枚举</span><span class="sxs-lookup"><span data-stu-id="53c84-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
