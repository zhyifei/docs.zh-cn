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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae87ebd0b8225f14ca029fac80528d47f5a866cf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799057"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="a1f46-102">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="a1f46-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="a1f46-103">从私钥/公钥对中获取公钥。</span><span class="sxs-lookup"><span data-stu-id="a1f46-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="a1f46-104">密钥对可以作为加密服务提供程序（CSP）中的密钥容器名称提供，也可以作为字节的原始集合提供。</span><span class="sxs-lookup"><span data-stu-id="a1f46-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="a1f46-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="a1f46-105">This function has been deprecated.</span></span> <span data-ttu-id="a1f46-106">改为使用[ICLRStrongName：： StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a1f46-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f46-107">语法</span><span class="sxs-lookup"><span data-stu-id="a1f46-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1f46-108">参数</span><span class="sxs-lookup"><span data-stu-id="a1f46-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="a1f46-109">中包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="a1f46-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="a1f46-110">如果`pbKeyBlob`为 null， `szKeyContainer`则必须在 CSP 内指定有效容器。</span><span class="sxs-lookup"><span data-stu-id="a1f46-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="a1f46-111">在这种情况`StrongNameGetPublicKey`下，从存储在容器中的密钥对中提取公钥。</span><span class="sxs-lookup"><span data-stu-id="a1f46-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="a1f46-112">如果`pbKeyBlob`不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。</span><span class="sxs-lookup"><span data-stu-id="a1f46-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="a1f46-113">密钥必须是1024位 Rivest-Rivest-shamir-adleman-Rivest-shamir-adleman （RSA）签名密钥。</span><span class="sxs-lookup"><span data-stu-id="a1f46-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="a1f46-114">此时不支持其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="a1f46-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a1f46-115">中指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="a1f46-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a1f46-116">此对采用 Win32 `CryptExportKey`函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="a1f46-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a1f46-117">如果`pbKeyBlob`为 null， `szKeyContainer`则假定指定的密钥容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="a1f46-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a1f46-118">中的`pbKeyBlob`大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a1f46-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="a1f46-119">弄返回的公钥 BLOB。</span><span class="sxs-lookup"><span data-stu-id="a1f46-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="a1f46-120">`ppbPublicKeyBlob`参数由公共语言运行时分配并返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="a1f46-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="a1f46-121">调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放内存。</span><span class="sxs-lookup"><span data-stu-id="a1f46-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="a1f46-122">弄返回的公钥 BLOB 的大小。</span><span class="sxs-lookup"><span data-stu-id="a1f46-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1f46-123">返回值</span><span class="sxs-lookup"><span data-stu-id="a1f46-123">Return Value</span></span>  
 <span data-ttu-id="a1f46-124">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="a1f46-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1f46-125">备注</span><span class="sxs-lookup"><span data-stu-id="a1f46-125">Remarks</span></span>  
 <span data-ttu-id="a1f46-126">公钥包含在[PublicKeyBlob](publickeyblob-structure.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="a1f46-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="a1f46-127">如果`StrongNameGetPublicKey`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="a1f46-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f46-128">要求</span><span class="sxs-lookup"><span data-stu-id="a1f46-128">Requirements</span></span>  
 <span data-ttu-id="a1f46-129">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1f46-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f46-130">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="a1f46-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a1f46-131">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a1f46-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1f46-132">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f46-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f46-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1f46-133">See also</span></span>

- [<span data-ttu-id="a1f46-134">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="a1f46-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="a1f46-135">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="a1f46-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="a1f46-136">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a1f46-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="a1f46-137">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="a1f46-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
