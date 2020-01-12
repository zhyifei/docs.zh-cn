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
ms.openlocfilehash: 1bfc41fdad35a7e0560d251179ea035c96aecab7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899522"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="c3216-102">ICLRStrongName::StrongNameSignatureVerificationFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="c3216-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="c3216-103">验证已映射到内存的程序集对关联的公钥是否有效。</span><span class="sxs-lookup"><span data-stu-id="c3216-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3216-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3216-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3216-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3216-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="c3216-106">中映射的程序集清单的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="c3216-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c3216-107">中映射的图像的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c3216-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="c3216-108">中影响验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="c3216-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="c3216-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="c3216-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="c3216-110">`SN_INFLAG_FORCE_VER` （0x00000001）-即使需要重写注册表设置，也强制进行验证。</span><span class="sxs-lookup"><span data-stu-id="c3216-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="c3216-111">`SN_INFLAG_INSTALL` （0x00000002）-指定这是在此映像上执行的第一次验证。</span><span class="sxs-lookup"><span data-stu-id="c3216-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="c3216-112">`SN_INFLAG_ADMIN_ACCESS` （0x00000004）-指定缓存只允许具有管理权限的用户访问。</span><span class="sxs-lookup"><span data-stu-id="c3216-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="c3216-113">`SN_INFLAG_USER_ACCESS` （0x00000008）-指定只有当前用户才能访问该程序集。</span><span class="sxs-lookup"><span data-stu-id="c3216-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="c3216-114">`SN_INFLAG_ALL_ACCESS` （0x00000010）-指定缓存将不提供访问限制。</span><span class="sxs-lookup"><span data-stu-id="c3216-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="c3216-115">`SN_INFLAG_RUNTIME` （0x80000000）-保留用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="c3216-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="c3216-116">弄用于附加输出信息的标志。</span><span class="sxs-lookup"><span data-stu-id="c3216-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="c3216-117">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="c3216-117">The following value is supported:</span></span>  
  
- <span data-ttu-id="c3216-118">`SN_OUTFLAG_WAS_VERIFIED` （0x00000001）-此值设置为 `false` 以指定验证是否已成功（因为注册表设置）。</span><span class="sxs-lookup"><span data-stu-id="c3216-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3216-119">返回值</span><span class="sxs-lookup"><span data-stu-id="c3216-119">Return Value</span></span>  
 <span data-ttu-id="c3216-120">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="c3216-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3216-121">需求</span><span class="sxs-lookup"><span data-stu-id="c3216-121">Requirements</span></span>  
 <span data-ttu-id="c3216-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3216-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3216-123">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="c3216-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c3216-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c3216-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3216-125">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3216-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3216-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3216-126">See also</span></span>

- [<span data-ttu-id="c3216-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="c3216-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
