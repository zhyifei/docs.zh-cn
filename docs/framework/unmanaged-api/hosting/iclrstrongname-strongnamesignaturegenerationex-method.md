---
title: "ICLRStrongName::StrongNameSignatureGenerationEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureGenerationEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 247bcfa3c9f7a02dea331ff14948a00812fb06e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="799f7-102">ICLRStrongName::StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="799f7-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="799f7-103">为指定的程序集中，根据指定的标志生成的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="799f7-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="799f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="799f7-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="799f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="799f7-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="799f7-106">[in]包含将为其生成强名称签名的程序集清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="799f7-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="799f7-107">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="799f7-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="799f7-108">如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 中有效的容器。</span><span class="sxs-lookup"><span data-stu-id="799f7-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="799f7-109">在这种情况下，存储在容器的密钥对用于对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="799f7-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="799f7-110">如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="799f7-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="799f7-111">[in]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="799f7-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="799f7-112">此对采用以下格式创建由 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="799f7-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="799f7-113">如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="799f7-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="799f7-114">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="799f7-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="799f7-115">[out]指向公共语言运行时向其返回签名的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="799f7-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="799f7-116">如果`ppbSignatureBlob`是 null，运行时将签名存储在指定的文件中`wszFilePath`。</span><span class="sxs-lookup"><span data-stu-id="799f7-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="799f7-117">如果`ppbSignatureBlob`是不为 null，公共语言运行时分配的空间内进行返回签名。</span><span class="sxs-lookup"><span data-stu-id="799f7-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="799f7-118">调用方必须释放此空间使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="799f7-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="799f7-119">[out]以字节为单位，返回签名的大小。</span><span class="sxs-lookup"><span data-stu-id="799f7-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="799f7-120">[in]一个或多个以下值：</span><span class="sxs-lookup"><span data-stu-id="799f7-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="799f7-121">`SN_SIGN_ALL_FILES`(0x00000001)-重新计算所有链接的模块的哈希值。</span><span class="sxs-lookup"><span data-stu-id="799f7-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="799f7-122">`SN_TEST_SIGN`(0x00000002) — 程序集进行测试签名。</span><span class="sxs-lookup"><span data-stu-id="799f7-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="799f7-123">返回值</span><span class="sxs-lookup"><span data-stu-id="799f7-123">Return Value</span></span>  
 <span data-ttu-id="799f7-124">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="799f7-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="799f7-125">备注</span><span class="sxs-lookup"><span data-stu-id="799f7-125">Remarks</span></span>  
 <span data-ttu-id="799f7-126">指定为空`wszFilePath`来计算而无需创建签名的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="799f7-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="799f7-127">可以直接在文件中，存储或返回到调用方的签名。</span><span class="sxs-lookup"><span data-stu-id="799f7-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="799f7-128">如果`SN_SIGN_ALL_FILES`指定但不包含的公共密钥 (同时`pbKeyBlob`和`wszFilePath`都为 null 时)，重新计算链接的模块的哈希值，但该程序集未重新签名。</span><span class="sxs-lookup"><span data-stu-id="799f7-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="799f7-129">如果`SN_TEST_SIGN`指定，则不会修改公共语言运行时标头以指示程序集使用强名称签名。</span><span class="sxs-lookup"><span data-stu-id="799f7-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="799f7-130">惠?</span><span class="sxs-lookup"><span data-stu-id="799f7-130">Requirements</span></span>  
 <span data-ttu-id="799f7-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="799f7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="799f7-132">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="799f7-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="799f7-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="799f7-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="799f7-134">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="799f7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799f7-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="799f7-135">See Also</span></span>  
 [<span data-ttu-id="799f7-136">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="799f7-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="799f7-137">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="799f7-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
