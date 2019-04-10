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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 679afd7b1053043a7cc43304a544a516024a4696
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165772"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="43f6d-102">ICLRStrongName::StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="43f6d-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="43f6d-103">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="43f6d-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f6d-104">语法</span><span class="sxs-lookup"><span data-stu-id="43f6d-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43f6d-105">参数</span><span class="sxs-lookup"><span data-stu-id="43f6d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="43f6d-106">[in]包含为其生成强名称签名的程序集的清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="43f6d-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="43f6d-107">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="43f6d-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="43f6d-108">如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 内有效的容器。</span><span class="sxs-lookup"><span data-stu-id="43f6d-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="43f6d-109">在这种情况下，使用容器中存储的密钥对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="43f6d-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="43f6d-110">如果`pbKeyBlob`不为 null，则假定为密钥对要包含在密钥二进制大型对象 (BLOB) 中。</span><span class="sxs-lookup"><span data-stu-id="43f6d-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="43f6d-111">键必须是 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="43f6d-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="43f6d-112">目前不支持任何其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="43f6d-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="43f6d-113">[in]一个指向公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="43f6d-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="43f6d-114">此对的格式创建的 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="43f6d-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="43f6d-115">如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="43f6d-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="43f6d-116">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="43f6d-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="43f6d-117">[out]指向该签名返回到公共语言运行时的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="43f6d-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="43f6d-118">如果`ppbSignatureBlob`是 null，则运行时存储签名中指定的文件`wszFilePath`。</span><span class="sxs-lookup"><span data-stu-id="43f6d-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="43f6d-119">如果`ppbSignatureBlob`是不为 null，公共语言运行时分配用于返回签名的空间。</span><span class="sxs-lookup"><span data-stu-id="43f6d-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="43f6d-120">调用方必须释放此空间使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="43f6d-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="43f6d-121">[out]以字节为单位，返回的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="43f6d-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43f6d-122">返回值</span><span class="sxs-lookup"><span data-stu-id="43f6d-122">Return Value</span></span>  
 `S_OK` <span data-ttu-id="43f6d-123">如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="43f6d-123">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43f6d-124">备注</span><span class="sxs-lookup"><span data-stu-id="43f6d-124">Remarks</span></span>  
 <span data-ttu-id="43f6d-125">指定为 null`wszFilePath`来计算而无需创建签名的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="43f6d-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="43f6d-126">签名可以是直接存储在该文件，或返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="43f6d-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43f6d-127">要求</span><span class="sxs-lookup"><span data-stu-id="43f6d-127">Requirements</span></span>  
 <span data-ttu-id="43f6d-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43f6d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43f6d-129">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="43f6d-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="43f6d-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="43f6d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="43f6d-131">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="43f6d-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43f6d-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="43f6d-132">See also</span></span>

- [<span data-ttu-id="43f6d-133">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="43f6d-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="43f6d-134">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="43f6d-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
