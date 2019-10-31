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
ms.openlocfilehash: 6b473466aefc06dc83526e65f8ee9e37703ba9e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134954"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="d161a-102">ICLRStrongName::StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="d161a-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="d161a-103">获取一个值，该值指示所提供的路径处的程序集清单是否包含强名称签名，该签名根据指定的标志进行验证。</span><span class="sxs-lookup"><span data-stu-id="d161a-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d161a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d161a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d161a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d161a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d161a-106">中要验证的程序集的可移植可执行文件（.dll 或 .exe）的路径。</span><span class="sxs-lookup"><span data-stu-id="d161a-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="d161a-107">中用于修改验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="d161a-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="d161a-108">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="d161a-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="d161a-109">`SN_INFLAG_FORCE_VER` （0x00000001）-即使需要重写注册表设置，也强制进行验证。</span><span class="sxs-lookup"><span data-stu-id="d161a-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="d161a-110">`SN_INFLAG_INSTALL` （0x00000002）-指定这是第一次验证清单。</span><span class="sxs-lookup"><span data-stu-id="d161a-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="d161a-111">`SN_INFLAG_ADMIN_ACCESS` （0x00000004）-指定缓存只允许具有管理权限的用户访问。</span><span class="sxs-lookup"><span data-stu-id="d161a-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="d161a-112">`SN_INFLAG_USER_ACCESS` （0x00000008）-指定只有当前用户才能访问该程序集。</span><span class="sxs-lookup"><span data-stu-id="d161a-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="d161a-113">`SN_INFLAG_ALL_ACCESS` （0x00000010）-指定缓存将不提供访问限制。</span><span class="sxs-lookup"><span data-stu-id="d161a-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="d161a-114">`SN_INFLAG_RUNTIME` （0x80000000）-保留用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="d161a-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="d161a-115">弄指示强名称签名是否已验证的标志。</span><span class="sxs-lookup"><span data-stu-id="d161a-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="d161a-116">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="d161a-116">The following value is supported:</span></span>  
  
- <span data-ttu-id="d161a-117">`SN_OUTFLAG_WAS_VERIFIED` （0x00000001）-此值设置为 `false` 以指定验证是否已成功（因为注册表设置）。</span><span class="sxs-lookup"><span data-stu-id="d161a-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d161a-118">返回值</span><span class="sxs-lookup"><span data-stu-id="d161a-118">Return Value</span></span>  
 <span data-ttu-id="d161a-119">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="d161a-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d161a-120">要求</span><span class="sxs-lookup"><span data-stu-id="d161a-120">Requirements</span></span>  
 <span data-ttu-id="d161a-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d161a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d161a-122">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="d161a-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d161a-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d161a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d161a-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d161a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d161a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d161a-125">See also</span></span>

- [<span data-ttu-id="d161a-126">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="d161a-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="d161a-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="d161a-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
