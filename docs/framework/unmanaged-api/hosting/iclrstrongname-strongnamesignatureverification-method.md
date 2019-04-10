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
ms.openlocfilehash: f9fb7098c29768821cafad6662b646eb0e08a138
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212838"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="f862b-102">ICLRStrongName::StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="f862b-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="f862b-103">获取一个值，该值指示是否在提供的路径处的程序集清单包含强名称签名，验证根据指定的标志。</span><span class="sxs-lookup"><span data-stu-id="f862b-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f862b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f862b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f862b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f862b-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f862b-106">[in]要验证的程序集的可移植可执行文件 （.dll 或.exe） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="f862b-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="f862b-107">[in]若要修改的验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="f862b-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="f862b-108">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="f862b-108">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="f862b-109">(0x00000001)-强制实施验证，即使需要重写注册表设置。</span><span class="sxs-lookup"><span data-stu-id="f862b-109">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="f862b-110">(0x00000002)-指定这是首次验证清单。</span><span class="sxs-lookup"><span data-stu-id="f862b-110">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="f862b-111">(0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="f862b-111">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="f862b-112">(0x00000008)-指定程序集可以访问仅向当前用户。</span><span class="sxs-lookup"><span data-stu-id="f862b-112">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="f862b-113">(0x00000010)-指定缓存将提供不保证其访问限制。</span><span class="sxs-lookup"><span data-stu-id="f862b-113">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="f862b-114">(0x80000000)-保留以用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="f862b-114">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="f862b-115">[out]标志，该值指示是否已验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="f862b-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="f862b-116">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="f862b-116">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="f862b-117">(0x00000001)-此值设置为`false`指定注册表设置使验证成功。</span><span class="sxs-lookup"><span data-stu-id="f862b-117">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f862b-118">返回值</span><span class="sxs-lookup"><span data-stu-id="f862b-118">Return Value</span></span>  
 `S_OK` <span data-ttu-id="f862b-119">如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="f862b-119">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f862b-120">要求</span><span class="sxs-lookup"><span data-stu-id="f862b-120">Requirements</span></span>  
 <span data-ttu-id="f862b-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f862b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f862b-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f862b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f862b-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f862b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f862b-124">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f862b-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f862b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f862b-125">See also</span></span>

- [<span data-ttu-id="f862b-126">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="f862b-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="f862b-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f862b-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
