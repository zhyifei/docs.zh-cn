---
title: COR_PRF_RUNTIME_TYPE 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
ms.openlocfilehash: 26948261c571dbe963811e8e9631551685a63bdb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450371"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="7f78d-102">COR_PRF_RUNTIME_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="7f78d-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="7f78d-103">包含一些值，这些值指示公共语言运行时（CLR）的版本：在 Silverlight 中使用的 desktop 或 CoreCLR。</span><span class="sxs-lookup"><span data-stu-id="7f78d-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f78d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f78d-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="7f78d-105">Members</span><span class="sxs-lookup"><span data-stu-id="7f78d-105">Members</span></span>  
  
|<span data-ttu-id="7f78d-106">成员</span><span class="sxs-lookup"><span data-stu-id="7f78d-106">Member</span></span>|<span data-ttu-id="7f78d-107">说明</span><span class="sxs-lookup"><span data-stu-id="7f78d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="7f78d-108">CLR 的桌面版本。</span><span class="sxs-lookup"><span data-stu-id="7f78d-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="7f78d-109">Silverlight 中使用的 CLR 核心版本。</span><span class="sxs-lookup"><span data-stu-id="7f78d-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f78d-110">备注</span><span class="sxs-lookup"><span data-stu-id="7f78d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f78d-111">要求</span><span class="sxs-lookup"><span data-stu-id="7f78d-111">Requirements</span></span>  
 <span data-ttu-id="7f78d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f78d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f78d-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f78d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f78d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f78d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f78d-115">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f78d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f78d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f78d-116">See also</span></span>

- [<span data-ttu-id="7f78d-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="7f78d-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
