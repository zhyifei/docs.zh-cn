---
title: StrongNameSignatureVerificationEx2 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d2ac3788b68626eb04a6f2cbac995b8e5b4ebf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442577"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="266cb-102">StrongNameSignatureVerificationEx2 方法</span><span class="sxs-lookup"><span data-stu-id="266cb-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="266cb-103">验证强名称程序集签名，并提供从 ECMA 键到真实键的映射。</span><span class="sxs-lookup"><span data-stu-id="266cb-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="266cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="266cb-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="266cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="266cb-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="266cb-106">[in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="266cb-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="266cb-107">[in]`true`执行验证，即使它是需要重写注册表设置; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="266cb-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="266cb-108">[in]指向 ECMA 公共至关重要的真实键中的映射的用于验证。</span><span class="sxs-lookup"><span data-stu-id="266cb-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="266cb-109">[in]实际的 ECMA 公共密钥的长度。</span><span class="sxs-lookup"><span data-stu-id="266cb-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="266cb-110">[out]`true`强名称签名验证; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="266cb-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="266cb-111">此参数也设置为`false`如果验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="266cb-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="266cb-112">返回值</span><span class="sxs-lookup"><span data-stu-id="266cb-112">Return Value</span></span>  
 <span data-ttu-id="266cb-113">`S_OK` 如果验证成功，则否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="266cb-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="266cb-114">要求</span><span class="sxs-lookup"><span data-stu-id="266cb-114">Requirements</span></span>  
 <span data-ttu-id="266cb-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="266cb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="266cb-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="266cb-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="266cb-117">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="266cb-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="266cb-118">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="266cb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266cb-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="266cb-119">See Also</span></span>  
 [<span data-ttu-id="266cb-120">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="266cb-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="266cb-121">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="266cb-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="266cb-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="266cb-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
