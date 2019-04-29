---
title: COR_PRF_GC_REASON 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf97f25b1adc30b173fcd81812a4b197915cdd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775029"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="7c6da-102">COR_PRF_GC_REASON 枚举</span><span class="sxs-lookup"><span data-stu-id="7c6da-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="7c6da-103">指示当前发生垃圾回收的原因。</span><span class="sxs-lookup"><span data-stu-id="7c6da-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6da-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c6da-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="7c6da-105">成员</span><span class="sxs-lookup"><span data-stu-id="7c6da-105">Members</span></span>  
  
|<span data-ttu-id="7c6da-106">成员</span><span class="sxs-lookup"><span data-stu-id="7c6da-106">Member</span></span>|<span data-ttu-id="7c6da-107">描述</span><span class="sxs-lookup"><span data-stu-id="7c6da-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="7c6da-108">通过已引发垃圾回收<xref:System.GC.Collect%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7c6da-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="7c6da-109">原因是未指定。</span><span class="sxs-lookup"><span data-stu-id="7c6da-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c6da-110">要求</span><span class="sxs-lookup"><span data-stu-id="7c6da-110">Requirements</span></span>  
 <span data-ttu-id="7c6da-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c6da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c6da-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c6da-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c6da-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c6da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c6da-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c6da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6da-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c6da-115">See also</span></span>

- [<span data-ttu-id="7c6da-116">分析枚举</span><span class="sxs-lookup"><span data-stu-id="7c6da-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
