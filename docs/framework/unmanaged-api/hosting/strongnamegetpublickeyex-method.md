---
title: StrongNameGetPublicKeyEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5651415b9565f71e7c899996708c0b263bf0154a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487988"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="a9932-102">StrongNameGetPublicKeyEx 方法</span><span class="sxs-lookup"><span data-stu-id="a9932-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="a9932-103">从公钥/私钥对，获取的公钥，并指定哈希算法和签名算法。</span><span class="sxs-lookup"><span data-stu-id="a9932-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9932-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9932-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9932-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9932-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="a9932-106">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="a9932-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="a9932-107">如果`pbKeyBlob`为 null，`szKeyContainer`必须指定加密服务提供商 (CSP) 内有效的容器。</span><span class="sxs-lookup"><span data-stu-id="a9932-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="a9932-108">在这种情况下，`StrongNameGetPublicKeyEx`方法从容器中存储的密钥对中提取的公钥。</span><span class="sxs-lookup"><span data-stu-id="a9932-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="a9932-109">如果`pbKeyBlob`不为 null，则假定为密钥对要包含在密钥二进制大型对象 (BLOB) 中。</span><span class="sxs-lookup"><span data-stu-id="a9932-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="a9932-110">键必须是 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="a9932-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="a9932-111">目前不支持任何其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="a9932-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a9932-112">[in]一个指向公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="a9932-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a9932-113">此对的格式创建的 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="a9932-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a9932-114">如果`pbKeyBlob`是 null，指定的密钥容器`szKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="a9932-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a9932-115">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="a9932-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="a9932-116">[out]返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="a9932-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="a9932-117">`ppbPublicKeyBlob`参数是分配的公共语言运行时，返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="a9932-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="a9932-118">调用方必须使用释放内存[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a9932-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="a9932-119">[out]返回公钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="a9932-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="a9932-120">[in]程序集哈希算法。</span><span class="sxs-lookup"><span data-stu-id="a9932-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="a9932-121">请参阅接受的值的列表的备注部分。</span><span class="sxs-lookup"><span data-stu-id="a9932-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="a9932-122">[in]保留供将来使用;默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="a9932-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9932-123">返回值</span><span class="sxs-lookup"><span data-stu-id="a9932-123">Return Value</span></span>  
 <span data-ttu-id="a9932-124">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="a9932-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9932-125">备注</span><span class="sxs-lookup"><span data-stu-id="a9932-125">Remarks</span></span>  
 <span data-ttu-id="a9932-126">中包含的公钥[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="a9932-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9932-127">备注</span><span class="sxs-lookup"><span data-stu-id="a9932-127">Remarks</span></span>  
 <span data-ttu-id="a9932-128">下表显示了接受的值的集`uHashAlgId`参数。</span><span class="sxs-lookup"><span data-stu-id="a9932-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="a9932-129">name</span><span class="sxs-lookup"><span data-stu-id="a9932-129">Name</span></span>|<span data-ttu-id="a9932-130">值</span><span class="sxs-lookup"><span data-stu-id="a9932-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="a9932-131">无</span><span class="sxs-lookup"><span data-stu-id="a9932-131">None</span></span>|<span data-ttu-id="a9932-132">0</span><span class="sxs-lookup"><span data-stu-id="a9932-132">0</span></span>|  
|<span data-ttu-id="a9932-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="a9932-133">SHA-1</span></span>|<span data-ttu-id="a9932-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="a9932-134">0x8004</span></span>|  
|<span data-ttu-id="a9932-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="a9932-135">SHA-256</span></span>|<span data-ttu-id="a9932-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="a9932-136">0x800c</span></span>|  
|<span data-ttu-id="a9932-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="a9932-137">SHA-384</span></span>|<span data-ttu-id="a9932-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="a9932-138">0x800d</span></span>|  
|<span data-ttu-id="a9932-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="a9932-139">SHA-512</span></span>|<span data-ttu-id="a9932-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="a9932-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9932-141">要求</span><span class="sxs-lookup"><span data-stu-id="a9932-141">Requirements</span></span>  
 <span data-ttu-id="a9932-142">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9932-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9932-143">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a9932-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a9932-144">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a9932-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9932-145">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9932-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9932-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9932-146">See also</span></span>
- [<span data-ttu-id="a9932-147">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="a9932-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="a9932-148">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="a9932-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="a9932-149">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a9932-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="a9932-150">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="a9932-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
