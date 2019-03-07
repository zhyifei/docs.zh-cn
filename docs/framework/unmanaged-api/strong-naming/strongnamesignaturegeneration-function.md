---
title: StrongNameSignatureGeneration 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a55ff59d698a1ced689e23d9908ce6e273d8a9c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494540"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="b5bf7-102">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="b5bf7-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="b5bf7-103">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="b5bf7-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-104">This function has been deprecated.</span></span> <span data-ttu-id="b5bf7-105">使用[iclrstrongname:: Strongnamesignaturegeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5bf7-106">语法</span><span class="sxs-lookup"><span data-stu-id="b5bf7-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5bf7-107">参数</span><span class="sxs-lookup"><span data-stu-id="b5bf7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b5bf7-108">[in]包含为其生成强名称签名的程序集的清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="b5bf7-109">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="b5bf7-110">如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 内有效的容器。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="b5bf7-111">在这种情况下，使用容器中存储的密钥对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="b5bf7-112">如果`pbKeyBlob`不为 null，则假定为密钥对要包含在密钥二进制大型对象 (BLOB) 中。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="b5bf7-113">键必须是 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="b5bf7-114">目前不支持任何其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="b5bf7-115">[in]一个指向公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="b5bf7-116">此对的格式创建的 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="b5bf7-117">如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="b5bf7-118">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="b5bf7-119">[out]指向该签名返回到公共语言运行时的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="b5bf7-120">如果`ppbSignatureBlob`是 null，则运行时存储签名中指定的文件`wszFilePath`。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="b5bf7-121">如果`ppbSignatureBlob`是不为 null，公共语言运行时分配用于返回签名的空间。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="b5bf7-122">调用方必须释放此空间使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="b5bf7-123">[out]以字节为单位，返回的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5bf7-124">返回值</span><span class="sxs-lookup"><span data-stu-id="b5bf7-124">Return Value</span></span>  
 <span data-ttu-id="b5bf7-125">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5bf7-126">备注</span><span class="sxs-lookup"><span data-stu-id="b5bf7-126">Remarks</span></span>  
 <span data-ttu-id="b5bf7-127">指定为 null`wszFilePath`来计算而无需创建签名的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="b5bf7-128">签名可以是直接存储在该文件，或返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="b5bf7-129">如果`StrongNameSignatureGeneration`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5bf7-130">要求</span><span class="sxs-lookup"><span data-stu-id="b5bf7-130">Requirements</span></span>  
 <span data-ttu-id="b5bf7-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5bf7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5bf7-132">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b5bf7-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b5bf7-133">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b5bf7-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5bf7-134">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5bf7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5bf7-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5bf7-135">See also</span></span>
- [<span data-ttu-id="b5bf7-136">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="b5bf7-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="b5bf7-137">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="b5bf7-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="b5bf7-138">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="b5bf7-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
