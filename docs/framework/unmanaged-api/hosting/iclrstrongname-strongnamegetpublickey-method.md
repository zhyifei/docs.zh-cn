---
title: ICLRStrongName::StrongNameGetPublicKey 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b736e58a1a48a2bb4492b6b8ff58af1567babcf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434475"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="9fe94-102">ICLRStrongName::StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="9fe94-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="9fe94-103">获取从公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="9fe94-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="9fe94-104">可以提供的密钥对，为加密服务提供商 (CSP) 中的密钥容器名称或原始字节的集合。</span><span class="sxs-lookup"><span data-stu-id="9fe94-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe94-105">语法</span><span class="sxs-lookup"><span data-stu-id="9fe94-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fe94-106">参数</span><span class="sxs-lookup"><span data-stu-id="9fe94-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="9fe94-107">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="9fe94-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="9fe94-108">如果`pbKeyBlob`为 null，`szKeyContainer`必须指定一个有效的容器的 CSP 中。</span><span class="sxs-lookup"><span data-stu-id="9fe94-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="9fe94-109">在这种情况下， [iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)方法从容器中存储的密钥对中提取公钥。</span><span class="sxs-lookup"><span data-stu-id="9fe94-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="9fe94-110">如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="9fe94-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="9fe94-111">键必须为 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="9fe94-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="9fe94-112">这次不支持的密钥的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="9fe94-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9fe94-113">[in]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="9fe94-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9fe94-114">此对采用以下格式创建由 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="9fe94-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9fe94-115">如果`pbKeyBlob`是 null，指定的密钥容器`szKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="9fe94-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9fe94-116">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="9fe94-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="9fe94-117">[out]返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="9fe94-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="9fe94-118">`ppbPublicKeyBlob`参数是由公共语言运行时分配的和返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="9fe94-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="9fe94-119">调用方必须释放的内存使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9fe94-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="9fe94-120">[out]返回的公共密钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="9fe94-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fe94-121">返回值</span><span class="sxs-lookup"><span data-stu-id="9fe94-121">Return Value</span></span>  
 <span data-ttu-id="9fe94-122">`S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="9fe94-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fe94-123">备注</span><span class="sxs-lookup"><span data-stu-id="9fe94-123">Remarks</span></span>  
 <span data-ttu-id="9fe94-124">中包含的公钥[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9fe94-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fe94-125">要求</span><span class="sxs-lookup"><span data-stu-id="9fe94-125">Requirements</span></span>  
 <span data-ttu-id="9fe94-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe94-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe94-127">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9fe94-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9fe94-128">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9fe94-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fe94-129">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe94-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe94-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="9fe94-130">See Also</span></span>  
 [<span data-ttu-id="9fe94-131">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="9fe94-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="9fe94-132">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="9fe94-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="9fe94-133">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="9fe94-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
