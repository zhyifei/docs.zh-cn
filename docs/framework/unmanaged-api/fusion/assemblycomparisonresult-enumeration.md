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
ms.openlocfilehash: 0086906b23cc65825bbd54a54e544fa9ec7b211e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796264"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="8a338-102">AssemblyComparisonResult 枚举</span><span class="sxs-lookup"><span data-stu-id="8a338-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="8a338-103">指示由[CompareAssemblyIdentity](compareassemblyidentity-function.md)函数确定的两个程序集标识的等效性。</span><span class="sxs-lookup"><span data-stu-id="8a338-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a338-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a338-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="8a338-105">成员</span><span class="sxs-lookup"><span data-stu-id="8a338-105">Members</span></span>  
  
|<span data-ttu-id="8a338-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="8a338-106">Member name</span></span>|<span data-ttu-id="8a338-107">描述</span><span class="sxs-lookup"><span data-stu-id="8a338-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="8a338-108">指示比较匹配项中的所有程序集字段。</span><span class="sxs-lookup"><span data-stu-id="8a338-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="8a338-109">指示根据 .NET Framework 版本2.0 中的公共语言运行时版本（CLR）统一的程序集版本号，将程序集视为等效。</span><span class="sxs-lookup"><span data-stu-id="8a338-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="8a338-110">指示程序集的部分匹配，这些程序集基于 .NET Framework 2.0 中的程序集版本号的 CLR 统一。</span><span class="sxs-lookup"><span data-stu-id="8a338-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="8a338-111">指示程序集的部分匹配项。</span><span class="sxs-lookup"><span data-stu-id="8a338-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="8a338-112">指示程序集的部分匹配，这些程序集基于旧的版本号。</span><span class="sxs-lookup"><span data-stu-id="8a338-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="8a338-113">指示只与命名的程序集进行部分匹配。</span><span class="sxs-lookup"><span data-stu-id="8a338-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="8a338-114">指示程序集根据 .NET Framework 旧版本中的 CLR 统一版本号被视为等效的。</span><span class="sxs-lookup"><span data-stu-id="8a338-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="8a338-115">指示两个只命名的程序集的匹配项，这些程序集的版本号被忽略。</span><span class="sxs-lookup"><span data-stu-id="8a338-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="8a338-116">指示两个程序集之间未发生匹配。</span><span class="sxs-lookup"><span data-stu-id="8a338-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="8a338-117">指示除了仅部分匹配的版本号外，这两个程序集匹配。</span><span class="sxs-lookup"><span data-stu-id="8a338-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="8a338-118">指示两个程序集匹配，但其版本号不匹配。</span><span class="sxs-lookup"><span data-stu-id="8a338-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="8a338-119">指示非等效的原因未知。</span><span class="sxs-lookup"><span data-stu-id="8a338-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a338-120">要求</span><span class="sxs-lookup"><span data-stu-id="8a338-120">Requirements</span></span>  
 <span data-ttu-id="8a338-121">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a338-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a338-122">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="8a338-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8a338-123">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8a338-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a338-124">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a338-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a338-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a338-125">See also</span></span>

- [<span data-ttu-id="8a338-126">CompareAssemblyIdentity 函数</span><span class="sxs-lookup"><span data-stu-id="8a338-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="8a338-127">合成枚举</span><span class="sxs-lookup"><span data-stu-id="8a338-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
