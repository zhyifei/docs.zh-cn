---
title: "StrongNameGetPublicKeyEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameGetPublicKeyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e94498cc8841a95e1918d3f26bd19256793564ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="e9637-102">StrongNameGetPublicKeyEx 方法</span><span class="sxs-lookup"><span data-stu-id="e9637-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="e9637-103">公钥/私钥对，从获取的公共密钥，并指定哈希算法和签名算法。</span><span class="sxs-lookup"><span data-stu-id="e9637-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9637-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9637-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e9637-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9637-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="e9637-106">[in]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="e9637-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="e9637-107">如果`pbKeyBlob`为 null，`szKeyContainer`必须指定加密服务提供商 (CSP) 中有效的容器。</span><span class="sxs-lookup"><span data-stu-id="e9637-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="e9637-108">在这种情况下，`StrongNameGetPublicKeyEx`方法从容器中存储的密钥对中提取公钥。</span><span class="sxs-lookup"><span data-stu-id="e9637-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="e9637-109">如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="e9637-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="e9637-110">键必须为 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="e9637-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="e9637-111">这次不支持的密钥的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="e9637-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="e9637-112">[in]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="e9637-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="e9637-113">此对采用以下格式创建由 Win32`CryptExportKey`函数。</span><span class="sxs-lookup"><span data-stu-id="e9637-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="e9637-114">如果`pbKeyBlob`是 null，指定的密钥容器`szKeyContainer`假定包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="e9637-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="e9637-115">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="e9637-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="e9637-116">[out]返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="e9637-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="e9637-117">`ppbPublicKeyBlob`参数是由公共语言运行时分配的和返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="e9637-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="e9637-118">调用方必须释放的内存使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e9637-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="e9637-119">[out]返回的公共密钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="e9637-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="e9637-120">[in]程序集哈希算法。</span><span class="sxs-lookup"><span data-stu-id="e9637-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="e9637-121">请参阅接受的值列表的备注部分。</span><span class="sxs-lookup"><span data-stu-id="e9637-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="e9637-122">[in]留待将来使用;默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="e9637-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9637-123">返回值</span><span class="sxs-lookup"><span data-stu-id="e9637-123">Return Value</span></span>  
 <span data-ttu-id="e9637-124">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="e9637-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9637-125">备注</span><span class="sxs-lookup"><span data-stu-id="e9637-125">Remarks</span></span>  
 <span data-ttu-id="e9637-126">中包含的公钥[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e9637-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9637-127">备注</span><span class="sxs-lookup"><span data-stu-id="e9637-127">Remarks</span></span>  
 <span data-ttu-id="e9637-128">下表显示的可接受值的一套`uHashAlgId`参数。</span><span class="sxs-lookup"><span data-stu-id="e9637-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="e9637-129">name</span><span class="sxs-lookup"><span data-stu-id="e9637-129">Name</span></span>|<span data-ttu-id="e9637-130">“值”</span><span class="sxs-lookup"><span data-stu-id="e9637-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="e9637-131">无</span><span class="sxs-lookup"><span data-stu-id="e9637-131">None</span></span>|<span data-ttu-id="e9637-132">0</span><span class="sxs-lookup"><span data-stu-id="e9637-132">0</span></span>|  
|<span data-ttu-id="e9637-133">SHA 1</span><span class="sxs-lookup"><span data-stu-id="e9637-133">SHA-1</span></span>|<span data-ttu-id="e9637-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="e9637-134">0x8004</span></span>|  
|<span data-ttu-id="e9637-135">SHA 256</span><span class="sxs-lookup"><span data-stu-id="e9637-135">SHA-256</span></span>|<span data-ttu-id="e9637-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="e9637-136">0x800c</span></span>|  
|<span data-ttu-id="e9637-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="e9637-137">SHA-384</span></span>|<span data-ttu-id="e9637-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="e9637-138">0x800d</span></span>|  
|<span data-ttu-id="e9637-139">SHA 512</span><span class="sxs-lookup"><span data-stu-id="e9637-139">SHA-512</span></span>|<span data-ttu-id="e9637-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="e9637-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9637-141">惠?</span><span class="sxs-lookup"><span data-stu-id="e9637-141">Requirements</span></span>  
 <span data-ttu-id="e9637-142">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9637-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9637-143">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e9637-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e9637-144">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e9637-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9637-145">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9637-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9637-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9637-146">See Also</span></span>  
 [<span data-ttu-id="e9637-147">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="e9637-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="e9637-148">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="e9637-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="e9637-149">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e9637-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="e9637-150">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="e9637-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
