---
title: "COR_PRF_CLAUSE_TYPE 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CLAUSE_TYPE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CLAUSE_TYPE
helpviewer_keywords: COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e03b3f2462b8876bfba3cf7d0df40311935722f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="9cad9-102">COR_PRF_CLAUSE_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="9cad9-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="9cad9-103">指示代码刚进入或离开的异常子句的类型。</span><span class="sxs-lookup"><span data-stu-id="9cad9-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cad9-104">语法</span><span class="sxs-lookup"><span data-stu-id="9cad9-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="9cad9-105">成员</span><span class="sxs-lookup"><span data-stu-id="9cad9-105">Members</span></span>  
  
|<span data-ttu-id="9cad9-106">成员</span><span class="sxs-lookup"><span data-stu-id="9cad9-106">Member</span></span>|<span data-ttu-id="9cad9-107">描述</span><span class="sxs-lookup"><span data-stu-id="9cad9-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="9cad9-108">异常子句无效。</span><span class="sxs-lookup"><span data-stu-id="9cad9-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="9cad9-109">异常子句是一个筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="9cad9-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="9cad9-110">该异常子句是`catch`语句。</span><span class="sxs-lookup"><span data-stu-id="9cad9-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="9cad9-111">该异常子句是`finally`语句。</span><span class="sxs-lookup"><span data-stu-id="9cad9-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cad9-112">惠?</span><span class="sxs-lookup"><span data-stu-id="9cad9-112">Requirements</span></span>  
 <span data-ttu-id="9cad9-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cad9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cad9-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9cad9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9cad9-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cad9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cad9-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cad9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cad9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cad9-117">See Also</span></span>  
 [<span data-ttu-id="9cad9-118">分析枚举</span><span class="sxs-lookup"><span data-stu-id="9cad9-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
