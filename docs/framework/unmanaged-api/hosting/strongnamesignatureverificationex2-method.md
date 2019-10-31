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
ms.openlocfilehash: cf8d6b7e45c0012d223173c85a92fac4fb044c6c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141409"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="6b0a8-102">StrongNameSignatureVerificationEx2 方法</span><span class="sxs-lookup"><span data-stu-id="6b0a8-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="6b0a8-103">验证强名称程序集的签名，并提供从 ECMA 密钥到实际密钥的映射。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b0a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b0a8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b0a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b0a8-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="6b0a8-106">中要验证的程序集的可移植可执行文件（.exe 或 .dll）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="6b0a8-107">[in] `true` 执行验证，即使需要重写注册表设置，否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="6b0a8-108">中一个指针，指向用于验证的从 ECMA 公钥到实际密钥的映射。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="6b0a8-109">中实际 ECMA 公钥的长度。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="6b0a8-110">[out] 如果验证强名称签名，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="6b0a8-111">如果验证因为注册表设置而成功，则此参数也设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b0a8-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6b0a8-112">Return Value</span></span>  
 <span data-ttu-id="6b0a8-113">如果验证成功，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b0a8-114">要求</span><span class="sxs-lookup"><span data-stu-id="6b0a8-114">Requirements</span></span>  
 <span data-ttu-id="6b0a8-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b0a8-116">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="6b0a8-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6b0a8-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6b0a8-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b0a8-118">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b0a8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b0a8-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b0a8-119">See also</span></span>

- [<span data-ttu-id="6b0a8-120">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="6b0a8-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="6b0a8-121">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="6b0a8-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="6b0a8-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6b0a8-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
