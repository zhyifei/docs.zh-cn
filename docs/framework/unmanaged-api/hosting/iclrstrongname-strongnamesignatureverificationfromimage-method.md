---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8c2151494a2ddfc200edc9c6c6cc3f7639bcf19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728877"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="e3c1b-102">ICLRStrongName::StrongNameSignatureVerificationFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="e3c1b-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="e3c1b-103">验证已映射到内存的程序集对关联的公钥是否有效。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3c1b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3c1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3c1b-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="e3c1b-106">[in]相对虚拟地址的映射的程序集清单。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e3c1b-107">[in]以字节为单位，映射图像的大小。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="e3c1b-108">[in]影响验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="e3c1b-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e3c1b-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e3c1b-110">`SN_INFLAG_FORCE_VER` (0x00000001)-强制实施验证，即使需要重写注册表设置。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="e3c1b-111">`SN_INFLAG_INSTALL` (0x00000002)-指定在此映像上执行第一次验证。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="e3c1b-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="e3c1b-113">`SN_INFLAG_USER_ACCESS` (0x00000008)-指定程序集可以访问仅向当前用户。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="e3c1b-114">`SN_INFLAG_ALL_ACCESS` (0x00000010)-指定缓存将提供不保证其访问限制。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="e3c1b-115">`SN_INFLAG_RUNTIME` (0x80000000)-保留以用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="e3c1b-116">[out]有关其他输出信息标志。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="e3c1b-117">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e3c1b-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="e3c1b-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-此值设置为`false`指定注册表设置使验证成功。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3c1b-119">返回值</span><span class="sxs-lookup"><span data-stu-id="e3c1b-119">Return Value</span></span>  
 <span data-ttu-id="e3c1b-120">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3c1b-121">要求</span><span class="sxs-lookup"><span data-stu-id="e3c1b-121">Requirements</span></span>  
 <span data-ttu-id="e3c1b-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3c1b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3c1b-123">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e3c1b-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e3c1b-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e3c1b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3c1b-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3c1b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c1b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3c1b-126">See also</span></span>
- [<span data-ttu-id="e3c1b-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e3c1b-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
