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
ms.openlocfilehash: 3e4181cbd14674336133314acdcd6cdcf0c9ff6b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134933"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="194ca-102">ICLRStrongName::StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="194ca-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="194ca-103">获取一个值，该值指示所提供的路径处的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="194ca-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="194ca-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="194ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="194ca-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="194ca-106">中要验证的程序集的可移植可执行文件（.exe 或 .dll）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="194ca-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="194ca-107">[in] `true` 执行验证，即使需要重写注册表设置，否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="194ca-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="194ca-108">[out] 如果验证强名称签名，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="194ca-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="194ca-109">如果验证因为注册表设置而成功，则也会将 `pfWasVerified` 设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="194ca-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="194ca-110">返回值</span><span class="sxs-lookup"><span data-stu-id="194ca-110">Return Value</span></span>  
 <span data-ttu-id="194ca-111">如果验证成功，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="194ca-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="194ca-112">备注</span><span class="sxs-lookup"><span data-stu-id="194ca-112">Remarks</span></span>  
 <span data-ttu-id="194ca-113">[ICLRStrongName：： StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法提供类似于[ICLRStrongName：： StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)方法的功能。</span><span class="sxs-lookup"><span data-stu-id="194ca-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="194ca-114">但是， [ICLRStrongName：： StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)的第二个输入参数和输出参数的类型为 `BOOLEAN`，而不是 `DWORD`。</span><span class="sxs-lookup"><span data-stu-id="194ca-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="194ca-115">要求</span><span class="sxs-lookup"><span data-stu-id="194ca-115">Requirements</span></span>  
 <span data-ttu-id="194ca-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="194ca-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="194ca-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="194ca-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="194ca-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="194ca-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="194ca-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="194ca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="194ca-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="194ca-120">See also</span></span>

- [<span data-ttu-id="194ca-121">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="194ca-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="194ca-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="194ca-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
