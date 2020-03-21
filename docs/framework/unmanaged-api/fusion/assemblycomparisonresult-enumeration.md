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
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178293"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="7114a-102">AssemblyComparisonResult 枚举</span><span class="sxs-lookup"><span data-stu-id="7114a-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="7114a-103">指示由[比较装配标识](compareassemblyidentity-function.md)函数确定的两个程序集标识的等效性。</span><span class="sxs-lookup"><span data-stu-id="7114a-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7114a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7114a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7114a-105">成员</span><span class="sxs-lookup"><span data-stu-id="7114a-105">Members</span></span>  
  
|<span data-ttu-id="7114a-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="7114a-106">Member name</span></span>|<span data-ttu-id="7114a-107">说明</span><span class="sxs-lookup"><span data-stu-id="7114a-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="7114a-108">指示比较中的所有程序集字段匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="7114a-109">指示基于 .NET Framework 版本 2.0 中程序集版本 2.0 中程序集版本编号的通用语言运行时版本 （CLR） 统一，将程序集视为等效。</span><span class="sxs-lookup"><span data-stu-id="7114a-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="7114a-110">指示基于 .NET 框架 2.0 中程序集版本号的 CLR 统一的程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="7114a-111">指示程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="7114a-112">指示基于版本号的旧统一的程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="7114a-113">指示简单命名程序集的部分匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="7114a-114">指示基于 .NET Framework 旧版本中版本号的 CLR 统一，将程序集视为等效。</span><span class="sxs-lookup"><span data-stu-id="7114a-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="7114a-115">指示两个简单命名的程序集之间的匹配，其版本号被忽略。</span><span class="sxs-lookup"><span data-stu-id="7114a-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="7114a-116">指示两个程序集之间没有匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="7114a-117">指示两个程序集匹配，但版本号除外，只有部分匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="7114a-118">指示两个程序集匹配，但版本号不匹配。</span><span class="sxs-lookup"><span data-stu-id="7114a-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="7114a-119">指示非等价的原因尚不清楚。</span><span class="sxs-lookup"><span data-stu-id="7114a-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7114a-120">要求</span><span class="sxs-lookup"><span data-stu-id="7114a-120">Requirements</span></span>  
 <span data-ttu-id="7114a-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7114a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7114a-122">**标题：** 融合.h</span><span class="sxs-lookup"><span data-stu-id="7114a-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7114a-123">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="7114a-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7114a-124">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7114a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7114a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7114a-125">See also</span></span>

- [<span data-ttu-id="7114a-126">CompareAssemblyIdentity 函数</span><span class="sxs-lookup"><span data-stu-id="7114a-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="7114a-127">合成枚举</span><span class="sxs-lookup"><span data-stu-id="7114a-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
