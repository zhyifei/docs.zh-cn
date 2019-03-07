---
title: IsFrameworkAssembly 函数
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0fb4c98ff2c8b071f05b42aefed61485001e97f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480320"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="4e75c-102">IsFrameworkAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="4e75c-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="4e75c-103">获取一个值，该值指示指定的程序集是否已托管。</span><span class="sxs-lookup"><span data-stu-id="4e75c-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e75c-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e75c-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e75c-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e75c-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="4e75c-106">[in]要检查的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="4e75c-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="4e75c-107">[out]一个布尔值，该值指示是否为托管程序集。</span><span class="sxs-lookup"><span data-stu-id="4e75c-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="4e75c-108">[in]一个 uncanonicalized 的字符串，包含程序集的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="4e75c-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="4e75c-109">[输入] `pwzFrameworkAssemblyIdentity` 的大小。</span><span class="sxs-lookup"><span data-stu-id="4e75c-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e75c-110">备注</span><span class="sxs-lookup"><span data-stu-id="4e75c-110">Remarks</span></span>  
 <span data-ttu-id="4e75c-111">`pwzAssemblyReference`参数是指向包含程序集名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="4e75c-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="4e75c-112">如果此程序集是.NET Framework 的一部分`pbIsFrameworkAssembly`参数将包含一个布尔值为`true`。</span><span class="sxs-lookup"><span data-stu-id="4e75c-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="4e75c-113">如果命名的程序集不是.NET Framework 的一部分，或如果`pwzAssemblyReference`参数没有命名程序集`pbIsFrameworkAssembly`将包含一个布尔值为`false`。</span><span class="sxs-lookup"><span data-stu-id="4e75c-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e75c-114">要求</span><span class="sxs-lookup"><span data-stu-id="4e75c-114">Requirements</span></span>  
 <span data-ttu-id="4e75c-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e75c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e75c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e75c-116">See also</span></span>
- [<span data-ttu-id="4e75c-117">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4e75c-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
