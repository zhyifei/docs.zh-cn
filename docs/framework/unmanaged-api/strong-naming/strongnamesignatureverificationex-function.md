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
ms.openlocfilehash: ca428d680df1710d8e74441d9945d4c3545b0482
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121144"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="42160-102">StrongNameSignatureVerificationEx 函数</span><span class="sxs-lookup"><span data-stu-id="42160-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="42160-103">获取一个值，该值指示提供的路径中的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="42160-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="42160-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="42160-104">This function has been deprecated.</span></span> <span data-ttu-id="42160-105">改为使用[ICLRStrongName：： StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="42160-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42160-106">语法</span><span class="sxs-lookup"><span data-stu-id="42160-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42160-107">参数</span><span class="sxs-lookup"><span data-stu-id="42160-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="42160-108">中要验证的程序集的可移植可执行文件（.exe 或 .dll）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="42160-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="42160-109">[in] `true` 执行验证，即使需要重写注册表设置，否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="42160-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="42160-110">[out] 如果验证强名称签名，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="42160-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="42160-111">如果验证因为注册表设置而成功，则也会将 `pfWasVerified` 设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="42160-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42160-112">返回值</span><span class="sxs-lookup"><span data-stu-id="42160-112">Return Value</span></span>  
 <span data-ttu-id="42160-113">如果验证成功，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="42160-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42160-114">备注</span><span class="sxs-lookup"><span data-stu-id="42160-114">Remarks</span></span>  
 <span data-ttu-id="42160-115">`StrongNameSignatureVerificationEx` 提供类似于[StrongNameSignatureVerification](strongnamesignatureverification-function.md)函数的功能。</span><span class="sxs-lookup"><span data-stu-id="42160-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="42160-116">但 `StrongNameSignatureVerificationEx` 的第二个输入参数和输出参数类型 `BOOLEAN` 而不是 `DWORD`。</span><span class="sxs-lookup"><span data-stu-id="42160-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42160-117">要求</span><span class="sxs-lookup"><span data-stu-id="42160-117">Requirements</span></span>  
 <span data-ttu-id="42160-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42160-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42160-119">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="42160-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="42160-120">**库：** 作为资源包括在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="42160-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="42160-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42160-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42160-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="42160-122">See also</span></span>

- [<span data-ttu-id="42160-123">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="42160-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="42160-124">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="42160-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="42160-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="42160-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
