---
title: COR_PRF_STATIC_TYPE 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34a2ca5b505c504115af47402c3d92a05ec0676f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737622"
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="a4475-102">COR_PRF_STATIC_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="a4475-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="a4475-103">指示字段是否为静态的，并在字段为静态字段时指示应用于该字段的静态质量。</span><span class="sxs-lookup"><span data-stu-id="a4475-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="a4475-104">这些值可以组合使用位或运算来指示该字段具有多个不同的静态质量。</span><span class="sxs-lookup"><span data-stu-id="a4475-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4475-105">语法</span><span class="sxs-lookup"><span data-stu-id="a4475-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a4475-106">成员</span><span class="sxs-lookup"><span data-stu-id="a4475-106">Members</span></span>  
  
|<span data-ttu-id="a4475-107">成员</span><span class="sxs-lookup"><span data-stu-id="a4475-107">Member</span></span>|<span data-ttu-id="a4475-108">描述</span><span class="sxs-lookup"><span data-stu-id="a4475-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="a4475-109">该字段不是静态的。</span><span class="sxs-lookup"><span data-stu-id="a4475-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="a4475-110">该字段是应用程序域静态。</span><span class="sxs-lookup"><span data-stu-id="a4475-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="a4475-111">线程静态字段。</span><span class="sxs-lookup"><span data-stu-id="a4475-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="a4475-112">该字段为静态上下文。</span><span class="sxs-lookup"><span data-stu-id="a4475-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="a4475-113">该字段是相对虚拟地址 (RVA) 的静态。</span><span class="sxs-lookup"><span data-stu-id="a4475-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4475-114">要求</span><span class="sxs-lookup"><span data-stu-id="a4475-114">Requirements</span></span>  
 <span data-ttu-id="a4475-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4475-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4475-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4475-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4475-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4475-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4475-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4475-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4475-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4475-119">See also</span></span>
- [<span data-ttu-id="a4475-120">分析枚举</span><span class="sxs-lookup"><span data-stu-id="a4475-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
