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
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181935"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="e24e8-102">ICLRStrongName::StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="e24e8-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="e24e8-103">从公钥/私钥对获取公钥。</span><span class="sxs-lookup"><span data-stu-id="e24e8-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="e24e8-104">密钥对可以作为加密服务提供商 （CSP） 中的密钥容器名称提供，也可以作为字节的原始集合提供。</span><span class="sxs-lookup"><span data-stu-id="e24e8-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e24e8-105">语法</span><span class="sxs-lookup"><span data-stu-id="e24e8-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e24e8-106">parameters</span><span class="sxs-lookup"><span data-stu-id="e24e8-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="e24e8-107">[在]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="e24e8-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="e24e8-108">如果`pbKeyBlob`为 null，`szKeyContainer`则必须在 CSP 中指定有效的容器。</span><span class="sxs-lookup"><span data-stu-id="e24e8-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="e24e8-109">在这种情况下[，ICLRStrongNameName：：StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)方法从存储在容器中的密钥对中提取公钥。</span><span class="sxs-lookup"><span data-stu-id="e24e8-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="e24e8-110">如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。</span><span class="sxs-lookup"><span data-stu-id="e24e8-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="e24e8-111">密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="e24e8-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="e24e8-112">目前不支持其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="e24e8-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="e24e8-113">[在]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="e24e8-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="e24e8-114">此对采用 Win32`CryptExportKey`函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="e24e8-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="e24e8-115">如果`pbKeyBlob`为 null，则假定 指定的`szKeyContainer`键容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="e24e8-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="e24e8-116">[在]的大小（以字节为单位）的大小`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="e24e8-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="e24e8-117">[出]返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="e24e8-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="e24e8-118">参数`ppbPublicKeyBlob`由通用语言运行时分配并返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="e24e8-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="e24e8-119">调用方必须使用[ICLRStrongNameName：：StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放内存。</span><span class="sxs-lookup"><span data-stu-id="e24e8-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="e24e8-120">[出]返回的公钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="e24e8-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e24e8-121">返回值</span><span class="sxs-lookup"><span data-stu-id="e24e8-121">Return Value</span></span>  
 <span data-ttu-id="e24e8-122">`S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="e24e8-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e24e8-123">备注</span><span class="sxs-lookup"><span data-stu-id="e24e8-123">Remarks</span></span>  
 <span data-ttu-id="e24e8-124">公钥包含在[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="e24e8-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e24e8-125">要求</span><span class="sxs-lookup"><span data-stu-id="e24e8-125">Requirements</span></span>  
 <span data-ttu-id="e24e8-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e24e8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e24e8-127">**标题：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e24e8-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e24e8-128">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="e24e8-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e24e8-129">**.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e24e8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e24e8-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e24e8-130">See also</span></span>

- [<span data-ttu-id="e24e8-131">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="e24e8-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="e24e8-132">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="e24e8-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="e24e8-133">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e24e8-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
