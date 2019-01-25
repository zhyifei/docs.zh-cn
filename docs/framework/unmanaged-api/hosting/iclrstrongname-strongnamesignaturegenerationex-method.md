---
title: ICLRStrongName::StrongNameSignatureGenerationEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f677fb738e66bcce4cabb66524e6083164ea3ec9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602736"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="4ae39-102">ICLRStrongName::StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="4ae39-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="4ae39-103">为指定的程序集，根据指定的标志生成的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4ae39-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae39-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ae39-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="4ae39-105">参数</span><span class="sxs-lookup"><span data-stu-id="4ae39-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4ae39-106">[in]包含为其生成强名称签名的程序集的清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4ae39-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="4ae39-107">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="4ae39-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="4ae39-108">如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 内有效的容器。</span><span class="sxs-lookup"><span data-stu-id="4ae39-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="4ae39-109">在这种情况下，使用容器中存储的密钥对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="4ae39-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="4ae39-110">如果`pbKeyBlob`不为 null，则假定为密钥对要包含在密钥二进制大型对象 (BLOB) 中。</span><span class="sxs-lookup"><span data-stu-id="4ae39-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="4ae39-111">[in]一个指向公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="4ae39-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="4ae39-112">此对的格式创建的 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="4ae39-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="4ae39-113">如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="4ae39-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="4ae39-114">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="4ae39-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="4ae39-115">[out]指向该签名返回到公共语言运行时的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="4ae39-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="4ae39-116">如果`ppbSignatureBlob`是 null，则运行时存储签名中指定的文件`wszFilePath`。</span><span class="sxs-lookup"><span data-stu-id="4ae39-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="4ae39-117">如果`ppbSignatureBlob`是不为 null，公共语言运行时分配用于返回签名的空间。</span><span class="sxs-lookup"><span data-stu-id="4ae39-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="4ae39-118">调用方必须释放此空间使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4ae39-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="4ae39-119">[out]以字节为单位，返回的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="4ae39-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4ae39-120">[in]一个或多个以下值：</span><span class="sxs-lookup"><span data-stu-id="4ae39-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="4ae39-121">`SN_SIGN_ALL_FILES` (0x00000001) 的重新计算链接的模块的所有哈希值。</span><span class="sxs-lookup"><span data-stu-id="4ae39-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="4ae39-122">`SN_TEST_SIGN` (0x00000002) — 测试签名程序集。</span><span class="sxs-lookup"><span data-stu-id="4ae39-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ae39-123">返回值</span><span class="sxs-lookup"><span data-stu-id="4ae39-123">Return Value</span></span>  
 <span data-ttu-id="4ae39-124">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="4ae39-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ae39-125">备注</span><span class="sxs-lookup"><span data-stu-id="4ae39-125">Remarks</span></span>  
 <span data-ttu-id="4ae39-126">指定为 null`wszFilePath`来计算而无需创建签名的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="4ae39-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="4ae39-127">可直接在文件中，存储或返回给调用方签名。</span><span class="sxs-lookup"><span data-stu-id="4ae39-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="4ae39-128">如果`SN_SIGN_ALL_FILES`指定但尚未包含的公共密钥 (同时`pbKeyBlob`和`wszFilePath`均为 null)，重新计算链接的模块的哈希值，但不重新签名程序集。</span><span class="sxs-lookup"><span data-stu-id="4ae39-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="4ae39-129">如果`SN_TEST_SIGN`指定，则公共语言运行时标头尚未修改以指示该程序集具有强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4ae39-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ae39-130">要求</span><span class="sxs-lookup"><span data-stu-id="4ae39-130">Requirements</span></span>  
 <span data-ttu-id="4ae39-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae39-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ae39-132">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4ae39-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4ae39-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4ae39-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ae39-134">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ae39-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae39-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ae39-135">See also</span></span>
- [<span data-ttu-id="4ae39-136">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="4ae39-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="4ae39-137">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="4ae39-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
