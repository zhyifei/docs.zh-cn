---
title: "ICLRStrongName::StrongNameSignatureGeneration 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureGeneration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcf872dcd1de34aaade06cf26914a75ae971b85b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="f8fcb-102">ICLRStrongName::StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="f8fcb-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="f8fcb-103">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8fcb-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8fcb-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f8fcb-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8fcb-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f8fcb-106">[in]包含将为其生成强名称签名的程序集清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="f8fcb-107">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="f8fcb-108">如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 中有效的容器。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="f8fcb-109">在这种情况下，存储在容器的密钥对用于对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="f8fcb-110">如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="f8fcb-111">键必须为 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="f8fcb-112">这次不支持的密钥的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f8fcb-113">[in]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="f8fcb-114">此对采用以下格式创建由 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="f8fcb-115">如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f8fcb-116">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="f8fcb-117">[out]指向公共语言运行时向其返回签名的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="f8fcb-118">如果`ppbSignatureBlob`是 null，运行时将签名存储在指定的文件中`wszFilePath`。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="f8fcb-119">如果`ppbSignatureBlob`是不为 null，公共语言运行时分配的空间内进行返回签名。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="f8fcb-120">调用方必须使用释放此空间[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="f8fcb-121">[out]以字节为单位，返回签名的大小。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8fcb-122">返回值</span><span class="sxs-lookup"><span data-stu-id="f8fcb-122">Return Value</span></span>  
 <span data-ttu-id="f8fcb-123">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8fcb-124">备注</span><span class="sxs-lookup"><span data-stu-id="f8fcb-124">Remarks</span></span>  
 <span data-ttu-id="f8fcb-125">指定为空`wszFilePath`来计算而无需创建签名的签名的大小。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="f8fcb-126">签名可以是直接存储在该文件，或返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8fcb-127">惠?</span><span class="sxs-lookup"><span data-stu-id="f8fcb-127">Requirements</span></span>  
 <span data-ttu-id="f8fcb-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8fcb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8fcb-129">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f8fcb-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f8fcb-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f8fcb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8fcb-131">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8fcb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8fcb-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8fcb-132">See Also</span></span>  
 [<span data-ttu-id="f8fcb-133">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="f8fcb-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="f8fcb-134">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f8fcb-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
