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
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176222"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="78919-102">StrongNameGetPublicKeyEx 方法</span><span class="sxs-lookup"><span data-stu-id="78919-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="78919-103">从公钥/私钥对获取公钥，并指定哈希算法和签名算法。</span><span class="sxs-lookup"><span data-stu-id="78919-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78919-104">语法</span><span class="sxs-lookup"><span data-stu-id="78919-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="78919-105">parameters</span><span class="sxs-lookup"><span data-stu-id="78919-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="78919-106">[在]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="78919-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="78919-107">如果`pbKeyBlob`为 null，`szKeyContainer`则必须在加密服务提供商 （CSP） 中指定有效的容器。</span><span class="sxs-lookup"><span data-stu-id="78919-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="78919-108">在这种情况下，`StrongNameGetPublicKeyEx`该方法从存储在容器中的密钥对中提取公钥。</span><span class="sxs-lookup"><span data-stu-id="78919-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="78919-109">如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。</span><span class="sxs-lookup"><span data-stu-id="78919-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="78919-110">密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="78919-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="78919-111">目前不支持其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="78919-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="78919-112">[在]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="78919-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="78919-113">此对采用 Win32`CryptExportKey`函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="78919-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="78919-114">如果`pbKeyBlob`为 null，则假定 指定的`szKeyContainer`键容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="78919-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="78919-115">[在]的大小（以字节为单位）的大小`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="78919-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="78919-116">[出]返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="78919-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="78919-117">参数`ppbPublicKeyBlob`由通用语言运行时分配并返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="78919-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="78919-118">调用方必须使用[ICLRStrongNameName：：StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放内存。</span><span class="sxs-lookup"><span data-stu-id="78919-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="78919-119">[出]返回的公钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="78919-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="78919-120">[在]程序集哈希算法。</span><span class="sxs-lookup"><span data-stu-id="78919-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="78919-121">有关已接受值的列表，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="78919-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="78919-122">[在]保留供将来使用;默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="78919-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78919-123">返回值</span><span class="sxs-lookup"><span data-stu-id="78919-123">Return Value</span></span>  
 <span data-ttu-id="78919-124">`S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="78919-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78919-125">备注</span><span class="sxs-lookup"><span data-stu-id="78919-125">Remarks</span></span>  
 <span data-ttu-id="78919-126">公钥包含在[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="78919-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78919-127">备注</span><span class="sxs-lookup"><span data-stu-id="78919-127">Remarks</span></span>  
 <span data-ttu-id="78919-128">下表显示了`uHashAlgId`参数的接受值集。</span><span class="sxs-lookup"><span data-stu-id="78919-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="78919-129">名称</span><span class="sxs-lookup"><span data-stu-id="78919-129">Name</span></span>|<span data-ttu-id="78919-130">值</span><span class="sxs-lookup"><span data-stu-id="78919-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="78919-131">无</span><span class="sxs-lookup"><span data-stu-id="78919-131">None</span></span>|<span data-ttu-id="78919-132">0</span><span class="sxs-lookup"><span data-stu-id="78919-132">0</span></span>|  
|<span data-ttu-id="78919-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="78919-133">SHA-1</span></span>|<span data-ttu-id="78919-134">0 x8004</span><span class="sxs-lookup"><span data-stu-id="78919-134">0x8004</span></span>|  
|<span data-ttu-id="78919-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="78919-135">SHA-256</span></span>|<span data-ttu-id="78919-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="78919-136">0x800c</span></span>|  
|<span data-ttu-id="78919-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="78919-137">SHA-384</span></span>|<span data-ttu-id="78919-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="78919-138">0x800d</span></span>|  
|<span data-ttu-id="78919-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="78919-139">SHA-512</span></span>|<span data-ttu-id="78919-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="78919-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78919-141">要求</span><span class="sxs-lookup"><span data-stu-id="78919-141">Requirements</span></span>  
 <span data-ttu-id="78919-142">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78919-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78919-143">**标题：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="78919-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="78919-144">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="78919-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78919-145">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78919-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78919-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78919-146">See also</span></span>

- [<span data-ttu-id="78919-147">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="78919-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="78919-148">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="78919-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="78919-149">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="78919-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="78919-150">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="78919-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
