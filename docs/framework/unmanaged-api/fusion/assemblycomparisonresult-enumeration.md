---
title: AssemblyComparisonResult 枚举
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b8ecc996e14263510e2d0a658cec020696c263
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141695"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="6e8c6-102">AssemblyComparisonResult 枚举</span><span class="sxs-lookup"><span data-stu-id="6e8c6-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="6e8c6-103">指示两个程序集标识的等效性，由[CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e8c6-104">Syntax</span></span>  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="6e8c6-105">成员</span><span class="sxs-lookup"><span data-stu-id="6e8c6-105">Members</span></span>  
  
|<span data-ttu-id="6e8c6-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="6e8c6-106">Member name</span></span>|<span data-ttu-id="6e8c6-107">描述</span><span class="sxs-lookup"><span data-stu-id="6e8c6-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="6e8c6-108">指示所有程序集在比较匹配字段。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="6e8c6-109">指示程序集都被视为等效基于.NET Framework 2.0 版中的程序集版本号的公共语言运行时 (CLR) 版本统一。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="6e8c6-110">指示基于 CLR 统一的.NET Framework 2.0 中的程序集版本号的程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="6e8c6-111">指示程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="6e8c6-112">指示基于旧统一的版本号的程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="6e8c6-113">指示只是名称的程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="6e8c6-114">指示程序集都被视为等效基于 CLR 统一在旧版本的.NET Framework 的版本号。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="6e8c6-115">指示两个简单命名程序集已忽略其版本号相匹配。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="6e8c6-116">指示两个程序集之间出现没有匹配项。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="6e8c6-117">指示两个程序集匹配除其版本号，仅部分匹配。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="6e8c6-118">指示两个程序集匹配但不匹配其版本号除外。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="6e8c6-119">指示不相等性的原因未知。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e8c6-120">要求</span><span class="sxs-lookup"><span data-stu-id="6e8c6-120">Requirements</span></span>  
 <span data-ttu-id="6e8c6-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e8c6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e8c6-122">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="6e8c6-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6e8c6-123">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6e8c6-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6e8c6-124">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6e8c6-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6e8c6-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e8c6-125">See also</span></span>

- [<span data-ttu-id="6e8c6-126">CompareAssemblyIdentity 函数</span><span class="sxs-lookup"><span data-stu-id="6e8c6-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [<span data-ttu-id="6e8c6-127">合成枚举</span><span class="sxs-lookup"><span data-stu-id="6e8c6-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
