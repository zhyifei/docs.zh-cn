---
title: "StrongNameSignatureVerification 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerification
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerification
helpviewer_keywords: StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2c04aba5b774b299e26be8dc532b894b6c6fad5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="b0cf3-102">StrongNameSignatureVerification 函数</span><span class="sxs-lookup"><span data-stu-id="b0cf3-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="b0cf3-103">获取一个值，该值在提供的路径的程序集清单是否包含强名称签名，验证根据指定的标志。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="b0cf3-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-104">This function has been deprecated.</span></span> <span data-ttu-id="b0cf3-105">使用[iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0cf3-106">语法</span><span class="sxs-lookup"><span data-stu-id="b0cf3-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0cf3-107">参数</span><span class="sxs-lookup"><span data-stu-id="b0cf3-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b0cf3-108">[in]要验证的程序集的可移植可执行文件 （.dll 或.exe） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="b0cf3-109">[in]若要修改的验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="b0cf3-110">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="b0cf3-110">The following values are supported:</span></span>  
  
-   <span data-ttu-id="b0cf3-111">`SN_INFLAG_FORCE_VER`(0x00000001) — 即使需要重写注册表设置强制执行验证。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="b0cf3-112">`SN_INFLAG_INSTALL`(0x00000002) — 指定这是首次验证清单。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="b0cf3-113">`SN_INFLAG_ADMIN_ACCESS`(0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="b0cf3-114">`SN_INFLAG_USER_ACCESS`(0x00000008)-指定程序集仅对当前用户可以访问。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="b0cf3-115">`SN_INFLAG_ALL_ACCESS`(0x00000010)-指定缓存将提供不能保证的访问限制。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="b0cf3-116">`SN_INFLAG_RUNTIME`(0x80000000)-保留供内部调试。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="b0cf3-117">[out]标志，指示是否已验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="b0cf3-118">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="b0cf3-118">The following value is supported:</span></span>  
  
-   <span data-ttu-id="b0cf3-119">`SN_OUTFLAG_WAS_VERIFIED`此值设置为 (0x00000001) —`false`指定验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0cf3-120">返回值</span><span class="sxs-lookup"><span data-stu-id="b0cf3-120">Return Value</span></span>  
 <span data-ttu-id="b0cf3-121">`true`如果验证成功，则否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0cf3-122">要求</span><span class="sxs-lookup"><span data-stu-id="b0cf3-122">Requirements</span></span>  
 <span data-ttu-id="b0cf3-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0cf3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0cf3-124">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b0cf3-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b0cf3-125">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b0cf3-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0cf3-126">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0cf3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0cf3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0cf3-127">See Also</span></span>  
 [<span data-ttu-id="b0cf3-128">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="b0cf3-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="b0cf3-129">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="b0cf3-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="b0cf3-130">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="b0cf3-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
