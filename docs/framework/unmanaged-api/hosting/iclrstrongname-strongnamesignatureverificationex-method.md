---
title: "ICLRStrongName::StrongNameSignatureVerificationEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureVerificationEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 047bc2212e1552a52f0eabf86cc0e86a6945ba39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="be66d-102">ICLRStrongName::StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="be66d-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="be66d-103">获取一个值，该值指示是否提供的路径的程序集清单包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="be66d-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be66d-104">语法</span><span class="sxs-lookup"><span data-stu-id="be66d-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be66d-105">参数</span><span class="sxs-lookup"><span data-stu-id="be66d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="be66d-106">[in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="be66d-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="be66d-107">[in]`true`执行验证，即使它是需要重写注册表设置; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="be66d-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="be66d-108">[out]`true`强名称签名验证; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="be66d-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="be66d-109">`pfWasVerified`此外将设置为`false`如果验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="be66d-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be66d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="be66d-110">Return Value</span></span>  
 <span data-ttu-id="be66d-111">`S_OK`如果验证成功，则否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="be66d-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be66d-112">备注</span><span class="sxs-lookup"><span data-stu-id="be66d-112">Remarks</span></span>  
 <span data-ttu-id="be66d-113">[Iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法提供了类似于一功能[iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="be66d-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="be66d-114">但是，第二个输入参数和输出参数为[iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)属于类型`BOOLEAN`而不是`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="be66d-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be66d-115">惠?</span><span class="sxs-lookup"><span data-stu-id="be66d-115">Requirements</span></span>  
 <span data-ttu-id="be66d-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be66d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be66d-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="be66d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="be66d-118">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="be66d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be66d-119">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be66d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be66d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="be66d-120">See Also</span></span>  
 [<span data-ttu-id="be66d-121">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="be66d-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="be66d-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="be66d-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
