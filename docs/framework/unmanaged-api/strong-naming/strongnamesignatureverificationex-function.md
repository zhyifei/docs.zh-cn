---
title: "StrongNameSignatureVerificationEx 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationEx
helpviewer_keywords: StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0aebb53c6718a6812cbe6a6888f389c7b1a52dda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="f2ad7-102">StrongNameSignatureVerificationEx 函数</span><span class="sxs-lookup"><span data-stu-id="f2ad7-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="f2ad7-103">获取一个值，该值在提供的路径的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="f2ad7-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-104">This function has been deprecated.</span></span> <span data-ttu-id="f2ad7-105">使用[iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ad7-106">语法</span><span class="sxs-lookup"><span data-stu-id="f2ad7-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2ad7-107">参数</span><span class="sxs-lookup"><span data-stu-id="f2ad7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f2ad7-108">[in]要验证的程序集的可移植可执行 （.exe 或.dll） 文件路径。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="f2ad7-109">[in]`true`执行验证，即使它是需要重写注册表设置; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="f2ad7-110">[out]`true`强名称签名验证; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="f2ad7-111">`pfWasVerified`此外将设置为`false`如果验证成功由于注册表设置。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2ad7-112">返回值</span><span class="sxs-lookup"><span data-stu-id="f2ad7-112">Return Value</span></span>  
 <span data-ttu-id="f2ad7-113">`true`如果验证成功，则否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ad7-114">备注</span><span class="sxs-lookup"><span data-stu-id="f2ad7-114">Remarks</span></span>  
 <span data-ttu-id="f2ad7-115">`StrongNameSignatureVerificationEx`提供了类似于一功能[StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="f2ad7-116">但是，第二个输入参数和输出参数为`StrongNameSignatureVerificationEx`属于类型`BOOLEAN`而不是`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ad7-117">要求</span><span class="sxs-lookup"><span data-stu-id="f2ad7-117">Requirements</span></span>  
 <span data-ttu-id="f2ad7-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2ad7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ad7-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f2ad7-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f2ad7-120">**库：**作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2ad7-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="f2ad7-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ad7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ad7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2ad7-122">See Also</span></span>  
 [<span data-ttu-id="f2ad7-123">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="f2ad7-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="f2ad7-124">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="f2ad7-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="f2ad7-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f2ad7-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
