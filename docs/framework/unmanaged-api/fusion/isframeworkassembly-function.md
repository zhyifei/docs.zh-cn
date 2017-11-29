---
title: "IsFrameworkAssembly 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IsFrameworkAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IsFrameworkAssembly
helpviewer_keywords: IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 216a7221550cb6345b29b5ed9e45b13ce40eadf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="1f342-102">IsFrameworkAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="1f342-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="1f342-103">获取一个值，该值指示指定的程序集是否为托管对象。</span><span class="sxs-lookup"><span data-stu-id="1f342-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f342-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f342-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f342-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f342-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="1f342-106">[in]要检查的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="1f342-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="1f342-107">[out]一个布尔值，该值指示是否已托管程序集。</span><span class="sxs-lookup"><span data-stu-id="1f342-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="1f342-108">[in]包含程序集的唯一标识一个 uncanonicalized 的字符串。</span><span class="sxs-lookup"><span data-stu-id="1f342-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="1f342-109">[输入] `pwzFrameworkAssemblyIdentity` 的大小。</span><span class="sxs-lookup"><span data-stu-id="1f342-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f342-110">备注</span><span class="sxs-lookup"><span data-stu-id="1f342-110">Remarks</span></span>  
 <span data-ttu-id="1f342-111">`pwzAssemblyReference`参数是指向包含程序集的名称的字符字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="1f342-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="1f342-112">如果此程序集是.NET Framework 的一部分`pbIsFrameworkAssembly`参数将包含布尔值的`true`。</span><span class="sxs-lookup"><span data-stu-id="1f342-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="1f342-113">如果指定的程序集不属于.NET Framework 中，或如果`pwzAssemblyReference`参数没有命名一个程序集，`pbIsFrameworkAssembly`将包含布尔值的`false`。</span><span class="sxs-lookup"><span data-stu-id="1f342-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f342-114">要求</span><span class="sxs-lookup"><span data-stu-id="1f342-114">Requirements</span></span>  
 <span data-ttu-id="1f342-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f342-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f342-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f342-116">See Also</span></span>  
 [<span data-ttu-id="1f342-117">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="1f342-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
