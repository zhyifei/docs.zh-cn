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
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798917"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="913a3-102">StrongNameSignatureVerificationEx 函数</span><span class="sxs-lookup"><span data-stu-id="913a3-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="913a3-103">获取一个值，该值指示提供的路径中的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="913a3-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="913a3-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="913a3-104">This function has been deprecated.</span></span> <span data-ttu-id="913a3-105">改为使用[ICLRStrongName：： StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="913a3-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="913a3-106">语法</span><span class="sxs-lookup"><span data-stu-id="913a3-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="913a3-107">参数</span><span class="sxs-lookup"><span data-stu-id="913a3-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="913a3-108">中要验证的程序集的可移植可执行文件（.exe 或 .dll）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="913a3-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="913a3-109">中如果需要重写注册表设置，则为; `false`否则为。 `true`</span><span class="sxs-lookup"><span data-stu-id="913a3-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="913a3-110">弄如果验证强名称签名， `false`则为; 否则为。 `true`</span><span class="sxs-lookup"><span data-stu-id="913a3-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="913a3-111">`pfWasVerified`如果验证因为注册表`false`设置而成功，则也会设置为。</span><span class="sxs-lookup"><span data-stu-id="913a3-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="913a3-112">返回值</span><span class="sxs-lookup"><span data-stu-id="913a3-112">Return Value</span></span>  
 <span data-ttu-id="913a3-113">`true`如果验证成功，则为;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="913a3-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="913a3-114">备注</span><span class="sxs-lookup"><span data-stu-id="913a3-114">Remarks</span></span>  
 <span data-ttu-id="913a3-115">`StrongNameSignatureVerificationEx`提供与[StrongNameSignatureVerification](strongnamesignatureverification-function.md)函数相似的功能。</span><span class="sxs-lookup"><span data-stu-id="913a3-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="913a3-116">但是，的第二个输入参数和输出参数`StrongNameSignatureVerificationEx`的类型`BOOLEAN`为，而`DWORD`不是。</span><span class="sxs-lookup"><span data-stu-id="913a3-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="913a3-117">要求</span><span class="sxs-lookup"><span data-stu-id="913a3-117">Requirements</span></span>  
 <span data-ttu-id="913a3-118">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="913a3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="913a3-119">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="913a3-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="913a3-120">**类库**作为资源包括在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="913a3-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="913a3-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="913a3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913a3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="913a3-122">See also</span></span>

- [<span data-ttu-id="913a3-123">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="913a3-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="913a3-124">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="913a3-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="913a3-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="913a3-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
