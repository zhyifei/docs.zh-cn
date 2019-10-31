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
ms.openlocfilehash: b95c96efeb666f25d04118aa8cb9b0da3a2e7924
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104164"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="7c1ef-102">StrongNameTokenFromPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="7c1ef-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="7c1ef-103">获取表示公钥的令牌。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-103">Gets a token representing a public key.</span></span> <span data-ttu-id="7c1ef-104">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="7c1ef-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-105">This function has been deprecated.</span></span> <span data-ttu-id="7c1ef-106">改为使用[ICLRStrongName：： StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1ef-107">语法</span><span class="sxs-lookup"><span data-stu-id="7c1ef-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c1ef-108">参数</span><span class="sxs-lookup"><span data-stu-id="7c1ef-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="7c1ef-109">中[PublicKeyBlob](publickeyblob-structure.md)类型的结构，它包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="7c1ef-110">中`pbPublicKeyBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="7c1ef-111">弄与 `pbPublicKeyBlob`中传递的密钥对应的强名称令牌。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="7c1ef-112">公共语言运行时分配要在其中返回标记的内存。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="7c1ef-113">调用方必须通过使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数来释放此内存。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="7c1ef-114">弄返回的强名称标记的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c1ef-115">返回值</span><span class="sxs-lookup"><span data-stu-id="7c1ef-115">Return Value</span></span>  
 <span data-ttu-id="7c1ef-116">成功完成后 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c1ef-117">备注</span><span class="sxs-lookup"><span data-stu-id="7c1ef-117">Remarks</span></span>  
 <span data-ttu-id="7c1ef-118">强名称标记是在元数据中存储密钥信息时用于节省空间的公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="7c1ef-119">具体而言，强名称令牌在程序集引用中用于引用依赖程序集。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="7c1ef-120">如果 `StrongNameTokenFromPublicKey` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c1ef-121">要求</span><span class="sxs-lookup"><span data-stu-id="7c1ef-121">Requirements</span></span>  
 <span data-ttu-id="7c1ef-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1ef-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c1ef-123">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="7c1ef-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7c1ef-124">**库：** 作为资源包括在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7c1ef-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="7c1ef-125">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c1ef-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1ef-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c1ef-126">See also</span></span>

- [<span data-ttu-id="7c1ef-127">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="7c1ef-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="7c1ef-128">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="7c1ef-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="7c1ef-129">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="7c1ef-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
