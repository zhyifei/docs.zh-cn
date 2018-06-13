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
ms.openlocfilehash: 28e6e95bbcca35ad39f30adcf100519748c02838
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449993"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="4b84a-102">COR_PRF_RUNTIME_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="4b84a-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="4b84a-103">包含指示公共语言运行时 (CLR) 的版本值： 桌面或 CoreCLR，Silverlight 中使用。</span><span class="sxs-lookup"><span data-stu-id="4b84a-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b84a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b84a-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="4b84a-105">成员</span><span class="sxs-lookup"><span data-stu-id="4b84a-105">Members</span></span>  
  
|<span data-ttu-id="4b84a-106">成员</span><span class="sxs-lookup"><span data-stu-id="4b84a-106">Member</span></span>|<span data-ttu-id="4b84a-107">描述</span><span class="sxs-lookup"><span data-stu-id="4b84a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="4b84a-108">CLR 桌面版本。</span><span class="sxs-lookup"><span data-stu-id="4b84a-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="4b84a-109">Silverlight 中所用的 CLR core 版本。</span><span class="sxs-lookup"><span data-stu-id="4b84a-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b84a-110">备注</span><span class="sxs-lookup"><span data-stu-id="4b84a-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b84a-111">要求</span><span class="sxs-lookup"><span data-stu-id="4b84a-111">Requirements</span></span>  
 <span data-ttu-id="4b84a-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b84a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b84a-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b84a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b84a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b84a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b84a-115">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b84a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b84a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b84a-116">See Also</span></span>  
 [<span data-ttu-id="4b84a-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="4b84a-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
