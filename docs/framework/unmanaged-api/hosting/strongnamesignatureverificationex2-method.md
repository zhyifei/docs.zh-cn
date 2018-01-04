---
title: "StrongNameSignatureVerificationEx2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4faa7fee32d9cab5a75772f29d2014473e2bee0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="d5dcd-102">StrongNameSignatureVerificationEx2 方法</span><span class="sxs-lookup"><span data-stu-id="d5dcd-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="d5dcd-103">验证强名称程序集签名，并提供从 ECMA 键到真实键的映射。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5dcd-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5dcd-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5dcd-105">参数</span><span class="sxs-lookup"><span data-stu-id="d5dcd-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d5dcd-106">[in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="d5dcd-107">[in]`true`执行验证，即使它是需要重写注册表设置; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="d5dcd-108">[in]指向 ECMA 公共至关重要的真实键中的映射的用于验证。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="d5dcd-109">[in]实际的 ECMA 公共密钥的长度。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="d5dcd-110">[out]`true`强名称签名验证; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="d5dcd-111">此参数也设置为`false`如果验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5dcd-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d5dcd-112">Return Value</span></span>  
 <span data-ttu-id="d5dcd-113">`S_OK`如果验证成功，则否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5dcd-114">惠?</span><span class="sxs-lookup"><span data-stu-id="d5dcd-114">Requirements</span></span>  
 <span data-ttu-id="d5dcd-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5dcd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5dcd-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d5dcd-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d5dcd-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d5dcd-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5dcd-118">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5dcd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5dcd-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5dcd-119">See Also</span></span>  
 [<span data-ttu-id="d5dcd-120">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="d5dcd-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="d5dcd-121">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="d5dcd-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="d5dcd-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="d5dcd-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
