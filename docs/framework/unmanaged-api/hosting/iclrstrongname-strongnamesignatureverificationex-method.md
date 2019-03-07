---
title: ICLRStrongName::StrongNameSignatureVerificationEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ce72f46b4cfc6098a95c4eb4b403e38a294a004
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472013"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="9e0e0-102">ICLRStrongName::StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="9e0e0-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="9e0e0-103">获取一个值，该值指示是否在提供的路径处的程序集清单包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e0e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e0e0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e0e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e0e0-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9e0e0-106">[in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="9e0e0-107">[in]`true`来执行验证，即使它是必须重写注册表设置; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="9e0e0-108">[out]`true`强名称签名是否已验证; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="9e0e0-109">`pfWasVerified` 此外将设置为`false`如果验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e0e0-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9e0e0-110">Return Value</span></span>  
 <span data-ttu-id="9e0e0-111">`S_OK` 如果验证成功;否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e0e0-112">备注</span><span class="sxs-lookup"><span data-stu-id="9e0e0-112">Remarks</span></span>  
 <span data-ttu-id="9e0e0-113">[Iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法提供的功能类似于[iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="9e0e0-114">但是，第二个输入参数和输出参数[iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)属于类型`BOOLEAN`而不是`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e0e0-115">要求</span><span class="sxs-lookup"><span data-stu-id="9e0e0-115">Requirements</span></span>  
 <span data-ttu-id="9e0e0-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e0e0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e0e0-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9e0e0-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9e0e0-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9e0e0-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e0e0-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e0e0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0e0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e0e0-120">See also</span></span>
- [<span data-ttu-id="9e0e0-121">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="9e0e0-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="9e0e0-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="9e0e0-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
