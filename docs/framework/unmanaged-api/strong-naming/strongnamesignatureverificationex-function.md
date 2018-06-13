---
title: StrongNameSignatureVerificationEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ce139669c0a31301f3eecdef4b4d61f83d5e4e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458934"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="01aa9-102">StrongNameSignatureVerificationEx 函数</span><span class="sxs-lookup"><span data-stu-id="01aa9-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="01aa9-103">获取一个值，该值在提供的路径的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="01aa9-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="01aa9-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="01aa9-104">This function has been deprecated.</span></span> <span data-ttu-id="01aa9-105">使用[iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="01aa9-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01aa9-106">语法</span><span class="sxs-lookup"><span data-stu-id="01aa9-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01aa9-107">参数</span><span class="sxs-lookup"><span data-stu-id="01aa9-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="01aa9-108">[in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="01aa9-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="01aa9-109">[in]`true`执行验证，即使它是需要重写注册表设置; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="01aa9-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="01aa9-110">[out]`true`强名称签名验证; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="01aa9-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="01aa9-111">`pfWasVerified` 此外将设置为`false`如果验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="01aa9-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01aa9-112">返回值</span><span class="sxs-lookup"><span data-stu-id="01aa9-112">Return Value</span></span>  
 <span data-ttu-id="01aa9-113">`true` 如果验证成功，则否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="01aa9-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01aa9-114">备注</span><span class="sxs-lookup"><span data-stu-id="01aa9-114">Remarks</span></span>  
 <span data-ttu-id="01aa9-115">`StrongNameSignatureVerificationEx` 提供了类似于一功能[StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="01aa9-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="01aa9-116">但是，第二个输入参数和输出参数为`StrongNameSignatureVerificationEx`属于类型`BOOLEAN`而不是`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="01aa9-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01aa9-117">要求</span><span class="sxs-lookup"><span data-stu-id="01aa9-117">Requirements</span></span>  
 <span data-ttu-id="01aa9-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01aa9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01aa9-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="01aa9-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="01aa9-120">**库：** 作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="01aa9-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="01aa9-121">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01aa9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01aa9-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="01aa9-122">See Also</span></span>  
 [<span data-ttu-id="01aa9-123">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="01aa9-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="01aa9-124">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="01aa9-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="01aa9-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="01aa9-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
