---
title: "COR_PRF_GC_REASON 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_REASON
helpviewer_keywords: COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75baeddd9c27dec6f110d461268ed546c167fc44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="91f1e-102">COR_PRF_GC_REASON 枚举</span><span class="sxs-lookup"><span data-stu-id="91f1e-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="91f1e-103">指示当前发生垃圾回收的原因。</span><span class="sxs-lookup"><span data-stu-id="91f1e-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f1e-104">语法</span><span class="sxs-lookup"><span data-stu-id="91f1e-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="91f1e-105">成员</span><span class="sxs-lookup"><span data-stu-id="91f1e-105">Members</span></span>  
  
|<span data-ttu-id="91f1e-106">成员</span><span class="sxs-lookup"><span data-stu-id="91f1e-106">Member</span></span>|<span data-ttu-id="91f1e-107">描述</span><span class="sxs-lookup"><span data-stu-id="91f1e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="91f1e-108">通过已引发垃圾回收<xref:System.GC.Collect%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="91f1e-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="91f1e-109">原因是未指定。</span><span class="sxs-lookup"><span data-stu-id="91f1e-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91f1e-110">惠?</span><span class="sxs-lookup"><span data-stu-id="91f1e-110">Requirements</span></span>  
 <span data-ttu-id="91f1e-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91f1e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f1e-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="91f1e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="91f1e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91f1e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91f1e-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f1e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f1e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="91f1e-115">See Also</span></span>  
 [<span data-ttu-id="91f1e-116">分析枚举</span><span class="sxs-lookup"><span data-stu-id="91f1e-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
