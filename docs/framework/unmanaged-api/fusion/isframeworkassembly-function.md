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
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796316"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="b0bff-102">IsFrameworkAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="b0bff-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="b0bff-103">获取一个值，该值指示是否托管指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="b0bff-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bff-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0bff-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0bff-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0bff-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="b0bff-106">中要检查的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="b0bff-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="b0bff-107">弄指示程序集是否为托管程序集的布尔值。</span><span class="sxs-lookup"><span data-stu-id="b0bff-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="b0bff-108">中一个 uncanonicalized 字符串，其中包含程序集的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="b0bff-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="b0bff-109">[输入] `pwzFrameworkAssemblyIdentity` 的大小。</span><span class="sxs-lookup"><span data-stu-id="b0bff-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0bff-110">备注</span><span class="sxs-lookup"><span data-stu-id="b0bff-110">Remarks</span></span>  
 <span data-ttu-id="b0bff-111">`pwzAssemblyReference`参数是指向字符串的指针，该字符串包含程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="b0bff-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="b0bff-112">如果此程序集是 .NET Framework 的一部分，则`pbIsFrameworkAssembly`参数将包含的`true`布尔值。</span><span class="sxs-lookup"><span data-stu-id="b0bff-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="b0bff-113">如果命名的程序集不是 .NET Framework 的一部分，或者如果`pwzAssemblyReference`参数不命名程序集， `pbIsFrameworkAssembly`则将包含的`false`布尔值。</span><span class="sxs-lookup"><span data-stu-id="b0bff-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0bff-114">要求</span><span class="sxs-lookup"><span data-stu-id="b0bff-114">Requirements</span></span>  
 <span data-ttu-id="b0bff-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0bff-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bff-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0bff-116">See also</span></span>

- [<span data-ttu-id="b0bff-117">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b0bff-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
