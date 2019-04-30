---
title: StrongNameTokenFromPublicKey 函数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbfd3ae32f4d3033894fdaf6b1bcc880c324e928
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000280"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="49a8d-102">StrongNameTokenFromPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="49a8d-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="49a8d-103">获取表示公钥的令牌。</span><span class="sxs-lookup"><span data-stu-id="49a8d-103">Gets a token representing a public key.</span></span> <span data-ttu-id="49a8d-104">强名称标记是简写形式的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="49a8d-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="49a8d-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="49a8d-105">This function has been deprecated.</span></span> <span data-ttu-id="49a8d-106">使用[iclrstrongname:: Strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="49a8d-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49a8d-107">语法</span><span class="sxs-lookup"><span data-stu-id="49a8d-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49a8d-108">参数</span><span class="sxs-lookup"><span data-stu-id="49a8d-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="49a8d-109">[in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) ，其中包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="49a8d-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="49a8d-110">[in]大小，以字节为单位的`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="49a8d-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="49a8d-111">[out]中的键相对应的强名称令牌传递`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="49a8d-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="49a8d-112">公共语言运行时分配的内存用于返回令牌。</span><span class="sxs-lookup"><span data-stu-id="49a8d-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="49a8d-113">调用方必须释放此内存通过使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="49a8d-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="49a8d-114">[out]以字节为单位，返回的强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="49a8d-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49a8d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="49a8d-115">Return Value</span></span>  
 <span data-ttu-id="49a8d-116">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="49a8d-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49a8d-117">备注</span><span class="sxs-lookup"><span data-stu-id="49a8d-117">Remarks</span></span>  
 <span data-ttu-id="49a8d-118">强名称标记是用来在元数据中存储密钥信息时节省空间的公共密钥使用缩写形式。</span><span class="sxs-lookup"><span data-stu-id="49a8d-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="49a8d-119">具体而言，强名称标记用于程序集引用中对依赖程序集，请参阅。</span><span class="sxs-lookup"><span data-stu-id="49a8d-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="49a8d-120">如果`StrongNameTokenFromPublicKey`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="49a8d-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49a8d-121">要求</span><span class="sxs-lookup"><span data-stu-id="49a8d-121">Requirements</span></span>  
 <span data-ttu-id="49a8d-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49a8d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49a8d-123">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="49a8d-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="49a8d-124">**库：** 包含为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="49a8d-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="49a8d-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49a8d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a8d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="49a8d-126">See also</span></span>

- [<span data-ttu-id="49a8d-127">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="49a8d-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="49a8d-128">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="49a8d-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="49a8d-129">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="49a8d-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
