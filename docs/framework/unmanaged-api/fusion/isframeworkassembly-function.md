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
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123073"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="62143-102">IsFrameworkAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="62143-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="62143-103">获取一个值，该值指示是否托管指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="62143-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62143-104">语法</span><span class="sxs-lookup"><span data-stu-id="62143-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="62143-105">参数</span><span class="sxs-lookup"><span data-stu-id="62143-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="62143-106">中要检查的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="62143-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="62143-107">弄指示程序集是否为托管程序集的布尔值。</span><span class="sxs-lookup"><span data-stu-id="62143-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="62143-108">中一个 uncanonicalized 字符串，其中包含程序集的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="62143-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="62143-109">[输入] `pwzFrameworkAssemblyIdentity` 的大小。</span><span class="sxs-lookup"><span data-stu-id="62143-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62143-110">备注</span><span class="sxs-lookup"><span data-stu-id="62143-110">Remarks</span></span>  
 <span data-ttu-id="62143-111">`pwzAssemblyReference` 参数是指向包含程序集名称的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="62143-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="62143-112">如果此程序集是 .NET Framework 的一部分，则 `pbIsFrameworkAssembly` 参数将包含一个 `true`的布尔值。</span><span class="sxs-lookup"><span data-stu-id="62143-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="62143-113">如果命名的程序集不是 .NET Framework 的一部分，或者 `pwzAssemblyReference` 参数未命名程序集，`pbIsFrameworkAssembly` 将包含一个布尔值 `false`。</span><span class="sxs-lookup"><span data-stu-id="62143-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62143-114">要求</span><span class="sxs-lookup"><span data-stu-id="62143-114">Requirements</span></span>  
 <span data-ttu-id="62143-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62143-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62143-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="62143-116">See also</span></span>

- [<span data-ttu-id="62143-117">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="62143-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
