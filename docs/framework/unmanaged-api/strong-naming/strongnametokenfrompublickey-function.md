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
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175052"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="c0c7c-102">StrongNameTokenFromPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="c0c7c-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="c0c7c-103">获取表示公钥的令牌。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-103">Gets a token representing a public key.</span></span> <span data-ttu-id="c0c7c-104">强名称令牌是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="c0c7c-105">此函数已被弃用。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-105">This function has been deprecated.</span></span> <span data-ttu-id="c0c7c-106">改用[ICLR 强名称：：强名称令牌来自公共密钥](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c7c-107">语法</span><span class="sxs-lookup"><span data-stu-id="c0c7c-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0c7c-108">parameters</span><span class="sxs-lookup"><span data-stu-id="c0c7c-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="c0c7c-109">[在][公共密钥Blob](publickeyblob-structure.md)类型的结构，其中包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="c0c7c-110">[在]的大小（以字节为单位）的大小`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c0c7c-111">[出]与传入的键对应的强名称令牌`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="c0c7c-112">通用语言运行时分配要返回令牌的内存。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="c0c7c-113">调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放此内存。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c0c7c-114">[出]返回的强名称令牌的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0c7c-115">返回值</span><span class="sxs-lookup"><span data-stu-id="c0c7c-115">Return Value</span></span>  
 <span data-ttu-id="c0c7c-116">`true`成功完成;否则， `false`.</span><span class="sxs-lookup"><span data-stu-id="c0c7c-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0c7c-117">备注</span><span class="sxs-lookup"><span data-stu-id="c0c7c-117">Remarks</span></span>  
 <span data-ttu-id="c0c7c-118">强名称令牌是公钥的缩写形式，用于在元数据中存储关键信息时节省空间。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="c0c7c-119">具体而言，强名称令牌用于程序集引用以引用从属程序集。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="c0c7c-120">如果`StrongNameTokenFromPublicKey`函数未成功完成，请调用[StrongNameErrorInfo 函数](strongnameerrorinfo-function.md)以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0c7c-121">要求</span><span class="sxs-lookup"><span data-stu-id="c0c7c-121">Requirements</span></span>  
 <span data-ttu-id="c0c7c-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0c7c-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0c7c-123">**标题：** 强名称.h</span><span class="sxs-lookup"><span data-stu-id="c0c7c-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c0c7c-124">**库：** 作为资源包含在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c0c7c-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="c0c7c-125">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0c7c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c7c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0c7c-126">See also</span></span>

- [<span data-ttu-id="c0c7c-127">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="c0c7c-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="c0c7c-128">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="c0c7c-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="c0c7c-129">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="c0c7c-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
