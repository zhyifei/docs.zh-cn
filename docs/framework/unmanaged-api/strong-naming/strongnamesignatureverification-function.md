---
title: StrongNameSignatureVerification 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3209b42263c62c8296d43ab06b0d89db2dd89be8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665992"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="d3efc-102">StrongNameSignatureVerification 函数</span><span class="sxs-lookup"><span data-stu-id="d3efc-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="d3efc-103">获取一个值，该值指示提供的路径中的程序集清单是否包含根据指定标志验证的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="d3efc-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="d3efc-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="d3efc-104">This function has been deprecated.</span></span> <span data-ttu-id="d3efc-105">使用[iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="d3efc-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3efc-106">语法</span><span class="sxs-lookup"><span data-stu-id="d3efc-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3efc-107">参数</span><span class="sxs-lookup"><span data-stu-id="d3efc-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d3efc-108">[in]要验证的程序集的可移植可执行文件 （.dll 或.exe） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="d3efc-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="d3efc-109">[in]若要修改的验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="d3efc-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="d3efc-110">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="d3efc-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="d3efc-111">`SN_INFLAG_FORCE_VER` (0x00000001)-强制实施验证，即使需要重写注册表设置。</span><span class="sxs-lookup"><span data-stu-id="d3efc-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="d3efc-112">`SN_INFLAG_INSTALL` (0x00000002)-指定这是首次验证清单。</span><span class="sxs-lookup"><span data-stu-id="d3efc-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="d3efc-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="d3efc-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="d3efc-114">`SN_INFLAG_USER_ACCESS` (0x00000008)-指定程序集可以访问仅向当前用户。</span><span class="sxs-lookup"><span data-stu-id="d3efc-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="d3efc-115">`SN_INFLAG_ALL_ACCESS` (0x00000010)-指定缓存将提供不保证其访问限制。</span><span class="sxs-lookup"><span data-stu-id="d3efc-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="d3efc-116">`SN_INFLAG_RUNTIME` (0x80000000)-保留以用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="d3efc-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="d3efc-117">[out]标志，该值指示是否已验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="d3efc-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="d3efc-118">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="d3efc-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="d3efc-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-此值设置为`false`指定注册表设置使验证成功。</span><span class="sxs-lookup"><span data-stu-id="d3efc-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3efc-120">返回值</span><span class="sxs-lookup"><span data-stu-id="d3efc-120">Return Value</span></span>  
 <span data-ttu-id="d3efc-121">`true` 如果验证成功;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="d3efc-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3efc-122">要求</span><span class="sxs-lookup"><span data-stu-id="d3efc-122">Requirements</span></span>  
 <span data-ttu-id="d3efc-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3efc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3efc-124">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d3efc-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d3efc-125">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d3efc-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3efc-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3efc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3efc-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3efc-127">See also</span></span>

- [<span data-ttu-id="d3efc-128">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="d3efc-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="d3efc-129">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="d3efc-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="d3efc-130">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="d3efc-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
