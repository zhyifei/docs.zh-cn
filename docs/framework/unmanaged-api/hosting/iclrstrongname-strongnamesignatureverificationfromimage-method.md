---
title: "ICLRStrongName::StrongNameSignatureVerificationFromImage 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57c8422d59a07de9ad045f2043594cb8d01f2f74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="6e3d1-102">ICLRStrongName::StrongNameSignatureVerificationFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="6e3d1-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="6e3d1-103">验证已映射到内存的程序集关联的公钥无效。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e3d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e3d1-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e3d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e3d1-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="6e3d1-106">[in]相对虚拟地址的映射程序集清单。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="6e3d1-107">[in]以字节为单位，映射的图像的大小。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="6e3d1-108">[in]影响验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="6e3d1-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="6e3d1-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="6e3d1-110">`SN_INFLAG_FORCE_VER`(0x00000001) — 即使需要重写注册表设置强制执行验证。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="6e3d1-111">`SN_INFLAG_INSTALL`(0x00000002) — 指定这是执行此映像上的第一个验证。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="6e3d1-112">`SN_INFLAG_ADMIN_ACCESS`(0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="6e3d1-113">`SN_INFLAG_USER_ACCESS`(0x00000008)-指定程序集仅对当前用户可以访问。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="6e3d1-114">`SN_INFLAG_ALL_ACCESS`(0x00000010)-指定缓存将提供不能保证的访问限制。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="6e3d1-115">`SN_INFLAG_RUNTIME`(0x80000000)-保留供内部调试。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="6e3d1-116">[out]有关其他输出信息标志。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="6e3d1-117">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="6e3d1-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="6e3d1-118">`SN_OUTFLAG_WAS_VERIFIED`此值设置为 (0x00000001) —`false`指定验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e3d1-119">返回值</span><span class="sxs-lookup"><span data-stu-id="6e3d1-119">Return Value</span></span>  
 <span data-ttu-id="6e3d1-120">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e3d1-121">惠?</span><span class="sxs-lookup"><span data-stu-id="6e3d1-121">Requirements</span></span>  
 <span data-ttu-id="6e3d1-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e3d1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e3d1-123">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6e3d1-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6e3d1-124">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6e3d1-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e3d1-125">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e3d1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3d1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e3d1-126">See Also</span></span>  
 [<span data-ttu-id="6e3d1-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6e3d1-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
