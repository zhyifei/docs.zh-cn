---
title: ICLRStrongName::StrongNameSignatureVerification 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49041031742332fbc275a9dbde91e640eb428c28
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210502"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="e1714-102">ICLRStrongName::StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="e1714-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="e1714-103">获取一个值，该值指示是否在提供的路径处的程序集清单包含强名称签名，验证根据指定的标志。</span><span class="sxs-lookup"><span data-stu-id="e1714-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1714-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1714-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1714-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1714-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e1714-106">[in]要验证的程序集的可移植可执行文件 （.dll 或.exe） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="e1714-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="e1714-107">[in]若要修改的验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="e1714-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="e1714-108">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e1714-108">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e1714-109">`SN_INFLAG_FORCE_VER` (0x00000001)-强制实施验证，即使需要重写注册表设置。</span><span class="sxs-lookup"><span data-stu-id="e1714-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="e1714-110">`SN_INFLAG_INSTALL` (0x00000002)-指定这是首次验证清单。</span><span class="sxs-lookup"><span data-stu-id="e1714-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="e1714-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="e1714-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="e1714-112">`SN_INFLAG_USER_ACCESS` (0x00000008)-指定程序集可以访问仅向当前用户。</span><span class="sxs-lookup"><span data-stu-id="e1714-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="e1714-113">`SN_INFLAG_ALL_ACCESS` (0x00000010)-指定缓存将提供不保证其访问限制。</span><span class="sxs-lookup"><span data-stu-id="e1714-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="e1714-114">`SN_INFLAG_RUNTIME` (0x80000000)-保留以用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="e1714-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="e1714-115">[out]标志，该值指示是否已验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="e1714-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="e1714-116">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e1714-116">The following value is supported:</span></span>  
  
-   <span data-ttu-id="e1714-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-此值设置为`false`指定注册表设置使验证成功。</span><span class="sxs-lookup"><span data-stu-id="e1714-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1714-118">返回值</span><span class="sxs-lookup"><span data-stu-id="e1714-118">Return Value</span></span>  
 <span data-ttu-id="e1714-119">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="e1714-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1714-120">要求</span><span class="sxs-lookup"><span data-stu-id="e1714-120">Requirements</span></span>  
 <span data-ttu-id="e1714-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1714-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1714-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e1714-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1714-123">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e1714-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1714-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1714-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1714-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1714-125">See Also</span></span>  
 [<span data-ttu-id="e1714-126">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="e1714-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="e1714-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e1714-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
