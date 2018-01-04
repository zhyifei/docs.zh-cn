---
title: "StrongNameTokenFromPublicKey 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: COM
f1_keywords: StrongNameTokenFromPublicKey
helpviewer_keywords: StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cb649f43bfea2e11c986aa3fff5a702e2b58c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="9b793-102">StrongNameTokenFromPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="9b793-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="9b793-103">获取表示公钥的标记。</span><span class="sxs-lookup"><span data-stu-id="9b793-103">Gets a token representing a public key.</span></span> <span data-ttu-id="9b793-104">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="9b793-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="9b793-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="9b793-105">This function has been deprecated.</span></span> <span data-ttu-id="9b793-106">使用[iclrstrongname:: Strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="9b793-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b793-107">语法</span><span class="sxs-lookup"><span data-stu-id="9b793-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b793-108">参数</span><span class="sxs-lookup"><span data-stu-id="9b793-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="9b793-109">[in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="9b793-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="9b793-110">[in]大小，以字节为单位的`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="9b793-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="9b793-111">[out]强名称标记的键对应传递中`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="9b793-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="9b793-112">公共语言运行时分配的内存中要返回的标记。</span><span class="sxs-lookup"><span data-stu-id="9b793-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="9b793-113">调用方必须释放此内存通过使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="9b793-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="9b793-114">[out]以字节为单位，返回的强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="9b793-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b793-115">返回值</span><span class="sxs-lookup"><span data-stu-id="9b793-115">Return Value</span></span>  
 <span data-ttu-id="9b793-116">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="9b793-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b793-117">备注</span><span class="sxs-lookup"><span data-stu-id="9b793-117">Remarks</span></span>  
 <span data-ttu-id="9b793-118">强名称标记是公钥的用于存储在元数据中的密钥信息时节省空间的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="9b793-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="9b793-119">具体而言，强名称令牌将用于程序集引用来引用依赖程序集。</span><span class="sxs-lookup"><span data-stu-id="9b793-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="9b793-120">如果`StrongNameTokenFromPublicKey`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="9b793-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b793-121">惠?</span><span class="sxs-lookup"><span data-stu-id="9b793-121">Requirements</span></span>  
 <span data-ttu-id="9b793-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b793-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b793-123">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9b793-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9b793-124">**库：**作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9b793-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="9b793-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b793-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b793-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b793-126">See Also</span></span>  
 [<span data-ttu-id="9b793-127">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="9b793-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="9b793-128">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="9b793-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="9b793-129">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="9b793-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
