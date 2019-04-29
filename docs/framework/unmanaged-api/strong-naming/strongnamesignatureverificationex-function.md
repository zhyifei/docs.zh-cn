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
ms.openlocfilehash: 049b7b11473a05d74dc311ca6ee79947039b0dd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794409"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="ef0d2-102">StrongNameSignatureVerificationEx 函数</span><span class="sxs-lookup"><span data-stu-id="ef0d2-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="ef0d2-103">获取一个值，该值指示提供的路径中的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="ef0d2-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-104">This function has been deprecated.</span></span> <span data-ttu-id="ef0d2-105">使用[iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef0d2-106">语法</span><span class="sxs-lookup"><span data-stu-id="ef0d2-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef0d2-107">参数</span><span class="sxs-lookup"><span data-stu-id="ef0d2-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ef0d2-108">[in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="ef0d2-109">[in]`true`来执行验证，即使它是必须重写注册表设置; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="ef0d2-110">[out]`true`强名称签名是否已验证; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="ef0d2-111">`pfWasVerified` 此外将设置为`false`如果验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef0d2-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ef0d2-112">Return Value</span></span>  
 <span data-ttu-id="ef0d2-113">`true` 如果验证成功;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef0d2-114">备注</span><span class="sxs-lookup"><span data-stu-id="ef0d2-114">Remarks</span></span>  
 <span data-ttu-id="ef0d2-115">`StrongNameSignatureVerificationEx` 提供的功能类似于[StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="ef0d2-116">但是，第二个输入参数和输出参数`StrongNameSignatureVerificationEx`属于类型`BOOLEAN`而不是`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef0d2-117">要求</span><span class="sxs-lookup"><span data-stu-id="ef0d2-117">Requirements</span></span>  
 <span data-ttu-id="ef0d2-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef0d2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef0d2-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ef0d2-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ef0d2-120">**库：** 包含为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ef0d2-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="ef0d2-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef0d2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0d2-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef0d2-122">See also</span></span>

- [<span data-ttu-id="ef0d2-123">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="ef0d2-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="ef0d2-124">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="ef0d2-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="ef0d2-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="ef0d2-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
