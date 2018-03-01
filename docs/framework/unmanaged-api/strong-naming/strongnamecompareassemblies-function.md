---
title: "StrongNameCompareAssemblies 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ed98b1713427a71c73c30ddd64188f61d51045c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="38d98-102">StrongNameCompareAssemblies 函数</span><span class="sxs-lookup"><span data-stu-id="38d98-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="38d98-103">确定是否两个程序集的差异仅在于其强名称签名。</span><span class="sxs-lookup"><span data-stu-id="38d98-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="38d98-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="38d98-104">This function has been deprecated.</span></span> <span data-ttu-id="38d98-105">使用[iclrstrongname:: Strongnamecompareassemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="38d98-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d98-106">语法</span><span class="sxs-lookup"><span data-stu-id="38d98-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38d98-107">参数</span><span class="sxs-lookup"><span data-stu-id="38d98-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="38d98-108">[in]第一个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="38d98-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="38d98-109">[in]第二个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="38d98-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="38d98-110">[out]以下值之一：</span><span class="sxs-lookup"><span data-stu-id="38d98-110">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="38d98-111">`SN_CMP_DIFFERENT`(0)-指定程序集包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="38d98-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="38d98-112">`SN_CMP_IDENTICAL`(1)-指定程序程序集完全相同，包括其签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="38d98-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="38d98-113">`SN_CMP_SIGONLY`(2)-指定程序集不同只能由签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="38d98-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38d98-114">返回值</span><span class="sxs-lookup"><span data-stu-id="38d98-114">Return Value</span></span>  
 <span data-ttu-id="38d98-115">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="38d98-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38d98-116">惠?</span><span class="sxs-lookup"><span data-stu-id="38d98-116">Requirements</span></span>  
 <span data-ttu-id="38d98-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38d98-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d98-118">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="38d98-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="38d98-119">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="38d98-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38d98-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d98-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38d98-121">备注</span><span class="sxs-lookup"><span data-stu-id="38d98-121">Remarks</span></span>  
 <span data-ttu-id="38d98-122">程序集的强名称签名组成程序集的文本名称、 版本、 区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="38d98-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="38d98-123">如果`StrongNameCompareAssemblies`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="38d98-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d98-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="38d98-124">See Also</span></span>  
 [<span data-ttu-id="38d98-125">StrongNameCompareAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="38d98-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [<span data-ttu-id="38d98-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="38d98-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
