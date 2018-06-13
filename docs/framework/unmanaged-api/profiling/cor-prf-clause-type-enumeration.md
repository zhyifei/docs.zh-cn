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
ms.openlocfilehash: f6909fa426fa952c0918638f40a571393c651e8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449928"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="ae063-102">COR_PRF_CLAUSE_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="ae063-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="ae063-103">指示代码刚进入或离开的异常子句的类型。</span><span class="sxs-lookup"><span data-stu-id="ae063-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae063-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae063-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="ae063-105">成员</span><span class="sxs-lookup"><span data-stu-id="ae063-105">Members</span></span>  
  
|<span data-ttu-id="ae063-106">成员</span><span class="sxs-lookup"><span data-stu-id="ae063-106">Member</span></span>|<span data-ttu-id="ae063-107">描述</span><span class="sxs-lookup"><span data-stu-id="ae063-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="ae063-108">异常子句无效。</span><span class="sxs-lookup"><span data-stu-id="ae063-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="ae063-109">异常子句是一个筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="ae063-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="ae063-110">该异常子句是`catch`语句。</span><span class="sxs-lookup"><span data-stu-id="ae063-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="ae063-111">该异常子句是`finally`语句。</span><span class="sxs-lookup"><span data-stu-id="ae063-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae063-112">要求</span><span class="sxs-lookup"><span data-stu-id="ae063-112">Requirements</span></span>  
 <span data-ttu-id="ae063-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae063-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae063-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae063-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae063-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae063-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae063-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae063-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae063-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae063-117">See Also</span></span>  
 [<span data-ttu-id="ae063-118">分析枚举</span><span class="sxs-lookup"><span data-stu-id="ae063-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
