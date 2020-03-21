---
title: StrongNameGetPublicKey 函数
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176924"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="ca984-102">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="ca984-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="ca984-103">从私钥/公钥对中获取公钥。</span><span class="sxs-lookup"><span data-stu-id="ca984-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="ca984-104">密钥对可以作为加密服务提供商 （CSP） 中的密钥容器名称提供，也可以作为字节的原始集合提供。</span><span class="sxs-lookup"><span data-stu-id="ca984-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="ca984-105">此函数已被弃用。</span><span class="sxs-lookup"><span data-stu-id="ca984-105">This function has been deprecated.</span></span> <span data-ttu-id="ca984-106">改用[ICLR 强名称：：强名称GetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ca984-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca984-107">语法</span><span class="sxs-lookup"><span data-stu-id="ca984-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca984-108">parameters</span><span class="sxs-lookup"><span data-stu-id="ca984-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="ca984-109">[在]包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="ca984-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="ca984-110">如果`pbKeyBlob`为 null，`szKeyContainer`则必须在 CSP 中指定有效的容器。</span><span class="sxs-lookup"><span data-stu-id="ca984-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="ca984-111">在这种情况下，`StrongNameGetPublicKey`从容器中存储的密钥对中提取公钥。</span><span class="sxs-lookup"><span data-stu-id="ca984-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="ca984-112">如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。</span><span class="sxs-lookup"><span data-stu-id="ca984-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="ca984-113">密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="ca984-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="ca984-114">目前不支持其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="ca984-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="ca984-115">[在]指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="ca984-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="ca984-116">此对采用 Win32`CryptExportKey`函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="ca984-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="ca984-117">如果`pbKeyBlob`为 null，则假定 指定的`szKeyContainer`键容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="ca984-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="ca984-118">[在]的大小（以字节为单位）的大小`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="ca984-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="ca984-119">[出]返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="ca984-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="ca984-120">参数`ppbPublicKeyBlob`由通用语言运行时分配并返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="ca984-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="ca984-121">调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放内存。</span><span class="sxs-lookup"><span data-stu-id="ca984-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="ca984-122">[出]返回的公钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="ca984-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca984-123">返回值</span><span class="sxs-lookup"><span data-stu-id="ca984-123">Return Value</span></span>  
 <span data-ttu-id="ca984-124">`true`成功完成;否则， `false`.</span><span class="sxs-lookup"><span data-stu-id="ca984-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca984-125">备注</span><span class="sxs-lookup"><span data-stu-id="ca984-125">Remarks</span></span>  
 <span data-ttu-id="ca984-126">公钥包含在[PublicKeyBlob](publickeyblob-structure.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="ca984-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="ca984-127">如果`StrongNameGetPublicKey`函数未成功完成，请调用[StrongNameErrorInfo 函数](strongnameerrorinfo-function.md)以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="ca984-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca984-128">要求</span><span class="sxs-lookup"><span data-stu-id="ca984-128">Requirements</span></span>  
 <span data-ttu-id="ca984-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca984-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca984-130">**标题：** 强名称.h</span><span class="sxs-lookup"><span data-stu-id="ca984-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ca984-131">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="ca984-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca984-132">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca984-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca984-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca984-133">See also</span></span>

- [<span data-ttu-id="ca984-134">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="ca984-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="ca984-135">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="ca984-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="ca984-136">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="ca984-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="ca984-137">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="ca984-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
