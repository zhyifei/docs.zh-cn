---
title: ICLRStrongName::StrongNameSignatureGeneration 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178041"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="4e94c-102">ICLRStrongName::StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="4e94c-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="4e94c-103">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4e94c-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e94c-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e94c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e94c-105">parameters</span><span class="sxs-lookup"><span data-stu-id="4e94c-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4e94c-106">[在]包含将为其生成强名称签名的程序集清单的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4e94c-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="4e94c-107">[在]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="4e94c-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="4e94c-108">如果`pbKeyBlob`为 null，`wszKeyContainer`则必须在加密服务提供商 （CSP） 中指定有效的容器。</span><span class="sxs-lookup"><span data-stu-id="4e94c-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="4e94c-109">在这种情况下，存储在容器中的密钥对用于对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="4e94c-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="4e94c-110">如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。</span><span class="sxs-lookup"><span data-stu-id="4e94c-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="4e94c-111">密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="4e94c-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="4e94c-112">目前不支持其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="4e94c-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="4e94c-113">[在]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="4e94c-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="4e94c-114">此对采用 Win32`CryptExportKey`函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="4e94c-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="4e94c-115">如果`pbKeyBlob`为 null，则假定 指定的`wszKeyContainer`键容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="4e94c-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="4e94c-116">[在]的大小（以字节为单位）的大小`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="4e94c-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="4e94c-117">[出]指向公共语言运行时返回签名的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="4e94c-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="4e94c-118">如果`ppbSignatureBlob`为 null，运行时将签名存储在 指定的`wszFilePath`文件中。</span><span class="sxs-lookup"><span data-stu-id="4e94c-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="4e94c-119">如果`ppbSignatureBlob`为 null，则通用语言运行时会分配用于返回签名的空间。</span><span class="sxs-lookup"><span data-stu-id="4e94c-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="4e94c-120">调用方必须使用[ICLRStrongNameName：：StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放此空间。</span><span class="sxs-lookup"><span data-stu-id="4e94c-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="4e94c-121">[出]返回的签名的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4e94c-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e94c-122">返回值</span><span class="sxs-lookup"><span data-stu-id="4e94c-122">Return Value</span></span>  
 <span data-ttu-id="4e94c-123">`S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="4e94c-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e94c-124">备注</span><span class="sxs-lookup"><span data-stu-id="4e94c-124">Remarks</span></span>  
 <span data-ttu-id="4e94c-125">指定 null`wszFilePath`以计算签名的大小而不创建签名。</span><span class="sxs-lookup"><span data-stu-id="4e94c-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="4e94c-126">签名可以直接存储在文件中，也可以返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="4e94c-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e94c-127">要求</span><span class="sxs-lookup"><span data-stu-id="4e94c-127">Requirements</span></span>  
 <span data-ttu-id="4e94c-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e94c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e94c-129">**标题：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4e94c-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4e94c-130">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="4e94c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e94c-131">**.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e94c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e94c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e94c-132">See also</span></span>

- [<span data-ttu-id="4e94c-133">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="4e94c-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="4e94c-134">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="4e94c-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
