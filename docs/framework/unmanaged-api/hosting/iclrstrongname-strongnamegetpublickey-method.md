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
ms.openlocfilehash: 943251357a91ea9ae3d492fa7bf20eebf948b8b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135079"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="bd81d-102">ICLRStrongName::StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="bd81d-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="bd81d-103">获取公钥/私钥对中的公钥。</span><span class="sxs-lookup"><span data-stu-id="bd81d-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="bd81d-104">密钥对可以作为加密服务提供程序（CSP）中的密钥容器名称提供，也可以作为字节的原始集合提供。</span><span class="sxs-lookup"><span data-stu-id="bd81d-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd81d-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd81d-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd81d-106">参数</span><span class="sxs-lookup"><span data-stu-id="bd81d-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="bd81d-107">中包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="bd81d-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="bd81d-108">如果 `pbKeyBlob` 为 null，则 `szKeyContainer` 必须在 CSP 中指定有效容器。</span><span class="sxs-lookup"><span data-stu-id="bd81d-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="bd81d-109">在这种情况下， [ICLRStrongName：： StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)方法将从存储在容器中的密钥对中提取公钥。</span><span class="sxs-lookup"><span data-stu-id="bd81d-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="bd81d-110">如果 `pbKeyBlob` 不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。</span><span class="sxs-lookup"><span data-stu-id="bd81d-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="bd81d-111">密钥必须是1024位 Rivest-Rivest-shamir-adleman-Rivest-shamir-adleman （RSA）签名密钥。</span><span class="sxs-lookup"><span data-stu-id="bd81d-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="bd81d-112">此时不支持其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="bd81d-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="bd81d-113">中指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="bd81d-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="bd81d-114">此对采用 Win32 `CryptExportKey` 函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="bd81d-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="bd81d-115">如果 `pbKeyBlob` 为 null，则假定 `szKeyContainer` 指定的密钥容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="bd81d-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="bd81d-116">中`pbKeyBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="bd81d-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="bd81d-117">弄返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="bd81d-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="bd81d-118">`ppbPublicKeyBlob` 参数由公共语言运行时分配并返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="bd81d-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="bd81d-119">调用方必须使用[ICLRStrongName：： StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放内存。</span><span class="sxs-lookup"><span data-stu-id="bd81d-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="bd81d-120">弄返回的公钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="bd81d-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd81d-121">返回值</span><span class="sxs-lookup"><span data-stu-id="bd81d-121">Return Value</span></span>  
 <span data-ttu-id="bd81d-122">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="bd81d-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd81d-123">备注</span><span class="sxs-lookup"><span data-stu-id="bd81d-123">Remarks</span></span>  
 <span data-ttu-id="bd81d-124">公钥包含在[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="bd81d-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd81d-125">要求</span><span class="sxs-lookup"><span data-stu-id="bd81d-125">Requirements</span></span>  
 <span data-ttu-id="bd81d-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd81d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd81d-127">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="bd81d-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bd81d-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="bd81d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd81d-129">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd81d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd81d-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd81d-130">See also</span></span>

- [<span data-ttu-id="bd81d-131">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="bd81d-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="bd81d-132">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="bd81d-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="bd81d-133">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="bd81d-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
