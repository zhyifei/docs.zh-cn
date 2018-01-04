---
title: "CompareAssemblyIdentity 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: CompareAssemblyIdentity
helpviewer_keywords: CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 266868a65a0db75b57d46d92a469b4b6ceaa88e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="44ac1-102">CompareAssemblyIdentity 函数</span><span class="sxs-lookup"><span data-stu-id="44ac1-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="44ac1-103">比较两个程序集标识，以确定它们是否等效。</span><span class="sxs-lookup"><span data-stu-id="44ac1-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ac1-104">语法</span><span class="sxs-lookup"><span data-stu-id="44ac1-104">Syntax</span></span>  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44ac1-105">参数</span><span class="sxs-lookup"><span data-stu-id="44ac1-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="44ac1-106">[in]文本中比较的第一个程序集标识。</span><span class="sxs-lookup"><span data-stu-id="44ac1-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="44ac1-107">[in]一个布尔型标志，该值指示用户指定的统一`pwzAssemblyIdentity1`。</span><span class="sxs-lookup"><span data-stu-id="44ac1-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="44ac1-108">[in]文本中比较的第二个程序集标识。</span><span class="sxs-lookup"><span data-stu-id="44ac1-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="44ac1-109">[in]一个布尔型标志，该值指示用户指定的统一`pwzAssemblyIdentity2`。</span><span class="sxs-lookup"><span data-stu-id="44ac1-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="44ac1-110">[out]一个布尔型标志，该值指示两个程序集是否等效。</span><span class="sxs-lookup"><span data-stu-id="44ac1-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="44ac1-111">[out][AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)枚举，其中包含有关比较的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="44ac1-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44ac1-112">返回值</span><span class="sxs-lookup"><span data-stu-id="44ac1-112">Return Value</span></span>  
 <span data-ttu-id="44ac1-113">`pfEquivalent`返回一个布尔值，该值指示两个程序集是否等效。</span><span class="sxs-lookup"><span data-stu-id="44ac1-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="44ac1-114">`pResult`返回的一个`AssemblyComparisonResult`值，以给出的值的详细的原因`pfEquivalent`。</span><span class="sxs-lookup"><span data-stu-id="44ac1-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44ac1-115">备注</span><span class="sxs-lookup"><span data-stu-id="44ac1-115">Remarks</span></span>  
 <span data-ttu-id="44ac1-116">`CompareAssemblyIdentity`检查是否`pwzAssemblyIdentity1`和`pwzAssemblyIdentity2`是等效的。</span><span class="sxs-lookup"><span data-stu-id="44ac1-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="44ac1-117">`pfEquivalent`设置为`true`下一个或多个以下条件：</span><span class="sxs-lookup"><span data-stu-id="44ac1-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
-   <span data-ttu-id="44ac1-118">两个程序集标识是等效的。</span><span class="sxs-lookup"><span data-stu-id="44ac1-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="44ac1-119">对于强名称程序集，等效性要求的程序集名称、 版本、 公钥标记和区域性视为相同。</span><span class="sxs-lookup"><span data-stu-id="44ac1-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="44ac1-120">对于只需名称的程序集，等效性要求匹配的程序集名称和区域性。</span><span class="sxs-lookup"><span data-stu-id="44ac1-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
-   <span data-ttu-id="44ac1-121">这两个程序集标识是指在.NET Framework 运行的程序集。</span><span class="sxs-lookup"><span data-stu-id="44ac1-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="44ac1-122">这种情况返回`true`即使不匹配的程序集版本号。</span><span class="sxs-lookup"><span data-stu-id="44ac1-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
-   <span data-ttu-id="44ac1-123">两个程序集不是托管程序集，但`fUnified1`或`fUnified2`已设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="44ac1-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="44ac1-124">`fUnified`标志指示最大为强名称程序集的版本号的所有版本数字均被都视为等效于强名称程序集。</span><span class="sxs-lookup"><span data-stu-id="44ac1-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="44ac1-125">例如，如果值`pwzAssemblyIndentity1`是"MyAssembly，版本 = 3.0.0.0，区域性 = neutral，publicKeyToken =..."，和的值`fUnified1`是`true`，这表示应从 0.0.0.0 到 3.0.0.0 版本起 MyAssembly 的所有版本视为等效项。</span><span class="sxs-lookup"><span data-stu-id="44ac1-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="44ac1-126">在这种情况下，如果`pwzAssemblyIndentity2`指的是相同的程序集中`pwzAssemblyIndentity1`，只不过它具有较低的版本号，`pfEquivalent`设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="44ac1-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="44ac1-127">如果`pwzAssemblyIdentity2`为更高版本的版本号，是指`pfEquivalent`设置为`true`才的值`fUnified2`是`true`。</span><span class="sxs-lookup"><span data-stu-id="44ac1-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="44ac1-128">`pResult`参数包括有关为什么两个程序集都被视为等效也不等效的特定信息。</span><span class="sxs-lookup"><span data-stu-id="44ac1-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="44ac1-129">有关详细信息，请参阅[AssemblyComparisonResult 枚举](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="44ac1-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44ac1-130">惠?</span><span class="sxs-lookup"><span data-stu-id="44ac1-130">Requirements</span></span>  
 <span data-ttu-id="44ac1-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44ac1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44ac1-132">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="44ac1-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="44ac1-133">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="44ac1-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44ac1-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44ac1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ac1-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="44ac1-135">See Also</span></span>  
 [<span data-ttu-id="44ac1-136">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="44ac1-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="44ac1-137">AssemblyComparisonResult 枚举</span><span class="sxs-lookup"><span data-stu-id="44ac1-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
