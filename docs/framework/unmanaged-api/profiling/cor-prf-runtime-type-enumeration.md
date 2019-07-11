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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c52f96ad9458dfd5cdedc5cc73154aa570c6759
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751963"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="d1dd1-102">COR_PRF_RUNTIME_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="d1dd1-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="d1dd1-103">包含指示公共语言运行时 (CLR) 的版本值： 桌面或 CoreCLR，在 Silverlight 中使用。</span><span class="sxs-lookup"><span data-stu-id="d1dd1-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1dd1-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1dd1-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="d1dd1-105">成员</span><span class="sxs-lookup"><span data-stu-id="d1dd1-105">Members</span></span>  
  
|<span data-ttu-id="d1dd1-106">成员</span><span class="sxs-lookup"><span data-stu-id="d1dd1-106">Member</span></span>|<span data-ttu-id="d1dd1-107">描述</span><span class="sxs-lookup"><span data-stu-id="d1dd1-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="d1dd1-108">桌面 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="d1dd1-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="d1dd1-109">在 Silverlight 中所用的 CLR core 版本。</span><span class="sxs-lookup"><span data-stu-id="d1dd1-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1dd1-110">备注</span><span class="sxs-lookup"><span data-stu-id="d1dd1-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1dd1-111">要求</span><span class="sxs-lookup"><span data-stu-id="d1dd1-111">Requirements</span></span>  
 <span data-ttu-id="d1dd1-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1dd1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1dd1-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1dd1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1dd1-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1dd1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1dd1-115">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1dd1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1dd1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1dd1-116">See also</span></span>

- [<span data-ttu-id="d1dd1-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="d1dd1-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
