---
title: StrongNameCompareAssemblies 函数
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0c2e8e46c7bb3a5e693c9ea16e6c5a0722b1898
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799149"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="51639-102">StrongNameCompareAssemblies 函数</span><span class="sxs-lookup"><span data-stu-id="51639-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="51639-103">确定两个程序集是否仅是强名称签名不同。</span><span class="sxs-lookup"><span data-stu-id="51639-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="51639-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="51639-104">This function has been deprecated.</span></span> <span data-ttu-id="51639-105">改为使用[ICLRStrongName：： StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="51639-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51639-106">语法</span><span class="sxs-lookup"><span data-stu-id="51639-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51639-107">参数</span><span class="sxs-lookup"><span data-stu-id="51639-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="51639-108">中第一个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="51639-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="51639-109">中第二个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="51639-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="51639-110">弄以下值之一：</span><span class="sxs-lookup"><span data-stu-id="51639-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="51639-111">`SN_CMP_DIFFERENT`（0）-指定程序集包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="51639-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="51639-112">`SN_CMP_IDENTICAL`（1）-指定程序集完全相同，包括它们的签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="51639-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="51639-113">`SN_CMP_SIGONLY`（2）-指定程序集不同于签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="51639-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51639-114">返回值</span><span class="sxs-lookup"><span data-stu-id="51639-114">Return Value</span></span>  
 <span data-ttu-id="51639-115">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="51639-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51639-116">要求</span><span class="sxs-lookup"><span data-stu-id="51639-116">Requirements</span></span>  
 <span data-ttu-id="51639-117">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51639-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51639-118">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="51639-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="51639-119">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="51639-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51639-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51639-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51639-121">备注</span><span class="sxs-lookup"><span data-stu-id="51639-121">Remarks</span></span>  
 <span data-ttu-id="51639-122">程序集的强名称签名由程序集的文本名称、版本、区域性和公钥标记组成。</span><span class="sxs-lookup"><span data-stu-id="51639-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="51639-123">如果 `StrongNameCompareAssemblies` 函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="51639-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51639-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="51639-124">See also</span></span>

- [<span data-ttu-id="51639-125">StrongNameCompareAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="51639-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="51639-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="51639-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
