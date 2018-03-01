---
title: "ICLRStrongName::StrongNameSignatureVerification 方法"
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
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1d8cb0ac6c671dae6ca5985e4082e2d3e71d89e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="dca2d-102">ICLRStrongName::StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="dca2d-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="dca2d-103">获取一个值，该值指示是否提供的路径的程序集清单包含强名称签名，验证根据指定的标志。</span><span class="sxs-lookup"><span data-stu-id="dca2d-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dca2d-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dca2d-105">参数</span><span class="sxs-lookup"><span data-stu-id="dca2d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="dca2d-106">[in]要验证的程序集的可移植可执行文件 （.dll 或.exe） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="dca2d-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="dca2d-107">[in]若要修改的验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="dca2d-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="dca2d-108">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="dca2d-108">The following values are supported:</span></span>  
  
-   <span data-ttu-id="dca2d-109">`SN_INFLAG_FORCE_VER`(0x00000001) — 即使需要重写注册表设置强制执行验证。</span><span class="sxs-lookup"><span data-stu-id="dca2d-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="dca2d-110">`SN_INFLAG_INSTALL`(0x00000002) — 指定这是首次验证清单。</span><span class="sxs-lookup"><span data-stu-id="dca2d-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="dca2d-111">`SN_INFLAG_ADMIN_ACCESS`(0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="dca2d-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="dca2d-112">`SN_INFLAG_USER_ACCESS`(0x00000008)-指定程序集仅对当前用户可以访问。</span><span class="sxs-lookup"><span data-stu-id="dca2d-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="dca2d-113">`SN_INFLAG_ALL_ACCESS`(0x00000010)-指定缓存将提供不能保证的访问限制。</span><span class="sxs-lookup"><span data-stu-id="dca2d-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="dca2d-114">`SN_INFLAG_RUNTIME`(0x80000000)-保留供内部调试。</span><span class="sxs-lookup"><span data-stu-id="dca2d-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="dca2d-115">[out]标志，指示是否已验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="dca2d-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="dca2d-116">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="dca2d-116">The following value is supported:</span></span>  
  
-   <span data-ttu-id="dca2d-117">`SN_OUTFLAG_WAS_VERIFIED`此值设置为 (0x00000001) —`false`指定验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="dca2d-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dca2d-118">返回值</span><span class="sxs-lookup"><span data-stu-id="dca2d-118">Return Value</span></span>  
 <span data-ttu-id="dca2d-119">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="dca2d-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca2d-120">惠?</span><span class="sxs-lookup"><span data-stu-id="dca2d-120">Requirements</span></span>  
 <span data-ttu-id="dca2d-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dca2d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca2d-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="dca2d-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dca2d-123">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dca2d-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dca2d-124">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca2d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca2d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="dca2d-125">See Also</span></span>  
 [<span data-ttu-id="dca2d-126">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="dca2d-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="dca2d-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="dca2d-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
