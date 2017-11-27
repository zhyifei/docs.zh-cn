---
title: "StrongNameSignatureVerificationFromImage 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationFromImage
helpviewer_keywords: StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab890451c44b19be6472ae6c7da060ae71612bc5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="f03b4-102">StrongNameSignatureVerificationFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="f03b4-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="f03b4-103">验证已映射到内存的程序集关联的公钥无效。</span><span class="sxs-lookup"><span data-stu-id="f03b4-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="f03b4-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="f03b4-104">This function has been deprecated.</span></span> <span data-ttu-id="f03b4-105">使用[ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="f03b4-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03b4-106">语法</span><span class="sxs-lookup"><span data-stu-id="f03b4-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f03b4-107">参数</span><span class="sxs-lookup"><span data-stu-id="f03b4-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="f03b4-108">[in]相对虚拟地址的映射程序集清单。</span><span class="sxs-lookup"><span data-stu-id="f03b4-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f03b4-109">[in]以字节为单位，映射的图像的大小。</span><span class="sxs-lookup"><span data-stu-id="f03b4-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="f03b4-110">[in]影响验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="f03b4-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="f03b4-111">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="f03b4-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="f03b4-112">`SN_INFLAG_FORCE_VER`(0x00000001) — 即使需要重写注册表设置强制执行验证。</span><span class="sxs-lookup"><span data-stu-id="f03b4-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="f03b4-113">`SN_INFLAG_INSTALL`(0x00000002) — 指定这是执行此映像上的第一个验证。</span><span class="sxs-lookup"><span data-stu-id="f03b4-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="f03b4-114">`SN_INFLAG_ADMIN_ACCESS`(0x00000004)-指定缓存将允许仅对具有管理权限的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="f03b4-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="f03b4-115">`SN_INFLAG_USER_ACCESS`(0x00000008)-指定程序集仅对当前用户可以访问。</span><span class="sxs-lookup"><span data-stu-id="f03b4-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="f03b4-116">`SN_INFLAG_ALL_ACCESS`(0x00000010)-指定缓存将提供不能保证的访问限制。</span><span class="sxs-lookup"><span data-stu-id="f03b4-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="f03b4-117">`SN_INFLAG_RUNTIME`(0x80000000)-保留供内部调试。</span><span class="sxs-lookup"><span data-stu-id="f03b4-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="f03b4-118">[out]有关其他输出信息标志。</span><span class="sxs-lookup"><span data-stu-id="f03b4-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="f03b4-119">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="f03b4-119">The following value is supported:</span></span>  
  
-   <span data-ttu-id="f03b4-120">`SN_OUTFLAG_WAS_VERIFIED`此值设置为 (0x00000001) —`false`指定验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="f03b4-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f03b4-121">返回值</span><span class="sxs-lookup"><span data-stu-id="f03b4-121">Return Value</span></span>  
 <span data-ttu-id="f03b4-122">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f03b4-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f03b4-123">备注</span><span class="sxs-lookup"><span data-stu-id="f03b4-123">Remarks</span></span>  
 <span data-ttu-id="f03b4-124">如果`StrongNameSignatureVerificationFromImage`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="f03b4-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f03b4-125">要求</span><span class="sxs-lookup"><span data-stu-id="f03b4-125">Requirements</span></span>  
 <span data-ttu-id="f03b4-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f03b4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f03b4-127">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f03b4-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f03b4-128">**库：**作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f03b4-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="f03b4-129">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f03b4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03b4-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f03b4-130">See Also</span></span>  
 [<span data-ttu-id="f03b4-131">StrongNameSignatureVerificationFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="f03b4-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [<span data-ttu-id="f03b4-132">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f03b4-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
