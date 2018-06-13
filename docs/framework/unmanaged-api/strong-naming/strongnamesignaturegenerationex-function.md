---
title: StrongNameSignatureGenerationEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ac2dd50b26137ee4cf06f0545f1f8cf1bfabf80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461638"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="484f7-102">StrongNameSignatureGenerationEx 函数</span><span class="sxs-lookup"><span data-stu-id="484f7-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="484f7-103">为指定的程序集中，根据指定的标志生成的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="484f7-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="484f7-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="484f7-104">This function has been deprecated.</span></span> <span data-ttu-id="484f7-105">使用[iclrstrongname:: Strongnamesignaturegenerationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="484f7-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="484f7-106">语法</span><span class="sxs-lookup"><span data-stu-id="484f7-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="484f7-107">参数</span><span class="sxs-lookup"><span data-stu-id="484f7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="484f7-108">[in]包含将为其生成强名称签名的程序集清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="484f7-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="484f7-109">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="484f7-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="484f7-110">如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 中有效的容器。</span><span class="sxs-lookup"><span data-stu-id="484f7-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="484f7-111">在这种情况下，存储在容器的密钥对用于对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="484f7-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="484f7-112">如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="484f7-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="484f7-113">[in]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="484f7-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="484f7-114">此对采用以下格式创建由 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="484f7-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="484f7-115">如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="484f7-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="484f7-116">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="484f7-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="484f7-117">[out]指向公共语言运行时向其返回签名的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="484f7-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="484f7-118">如果`ppbSignatureBlob`是 null，运行时将签名存储在指定的文件中`wszFilePath`。</span><span class="sxs-lookup"><span data-stu-id="484f7-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="484f7-119">如果`ppbSignatureBlob`是不为 null，公共语言运行时分配的空间内进行返回签名。</span><span class="sxs-lookup"><span data-stu-id="484f7-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="484f7-120">调用方必须释放此空间使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="484f7-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="484f7-121">[out]以字节为单位，返回签名的大小。</span><span class="sxs-lookup"><span data-stu-id="484f7-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="484f7-122">[in]一个或多个以下值：</span><span class="sxs-lookup"><span data-stu-id="484f7-122">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="484f7-123">`SN_SIGN_ALL_FILES` (0x00000001)-重新计算所有链接的模块的哈希值。</span><span class="sxs-lookup"><span data-stu-id="484f7-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="484f7-124">`SN_TEST_SIGN` (0x00000002) — 程序集进行测试签名。</span><span class="sxs-lookup"><span data-stu-id="484f7-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="484f7-125">返回值</span><span class="sxs-lookup"><span data-stu-id="484f7-125">Return Value</span></span>  
 <span data-ttu-id="484f7-126">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="484f7-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="484f7-127">备注</span><span class="sxs-lookup"><span data-stu-id="484f7-127">Remarks</span></span>  
 <span data-ttu-id="484f7-128">指定为空`wszFilePath`来计算而无需创建签名的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="484f7-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="484f7-129">可以直接在文件中，存储或返回到调用方的签名。</span><span class="sxs-lookup"><span data-stu-id="484f7-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="484f7-130">如果`SN_SIGN_ALL_FILES`指定但不包含的公共密钥 (同时`pbKeyBlob`和`wszFilePath`都为 null 时)，重新计算链接的模块的哈希值，但该程序集未重新签名。</span><span class="sxs-lookup"><span data-stu-id="484f7-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="484f7-131">如果`SN_TEST_SIGN`指定，则不会修改公共语言运行时标头以指示程序集使用强名称签名。</span><span class="sxs-lookup"><span data-stu-id="484f7-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="484f7-132">如果`StrongNameSignatureGenerationEx`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="484f7-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="484f7-133">要求</span><span class="sxs-lookup"><span data-stu-id="484f7-133">Requirements</span></span>  
 <span data-ttu-id="484f7-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="484f7-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="484f7-135">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="484f7-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="484f7-136">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="484f7-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="484f7-137">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="484f7-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="484f7-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="484f7-138">See Also</span></span>  
 [<span data-ttu-id="484f7-139">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="484f7-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="484f7-140">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="484f7-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="484f7-141">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="484f7-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
