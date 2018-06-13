---
title: ICLRStrongName::StrongNameTokenFromPublicKey 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 587e2086a03e9c9ba57ae3b68de841f12543404e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435603"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="121bd-102">ICLRStrongName::StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="121bd-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="121bd-103">获取令牌表示的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="121bd-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="121bd-104">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="121bd-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="121bd-105">语法</span><span class="sxs-lookup"><span data-stu-id="121bd-105">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="121bd-106">参数</span><span class="sxs-lookup"><span data-stu-id="121bd-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="121bd-107">[in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="121bd-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="121bd-108">[in]大小，以字节为单位的`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="121bd-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="121bd-109">[out]强名称标记的键对应传递中`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="121bd-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="121bd-110">公共语言运行时分配的内存中要返回的标记。</span><span class="sxs-lookup"><span data-stu-id="121bd-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="121bd-111">调用方必须释放此内存通过使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="121bd-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="121bd-112">[out]以字节为单位，返回的强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="121bd-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="121bd-113">返回值</span><span class="sxs-lookup"><span data-stu-id="121bd-113">Return Value</span></span>  
 <span data-ttu-id="121bd-114">`S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="121bd-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="121bd-115">备注</span><span class="sxs-lookup"><span data-stu-id="121bd-115">Remarks</span></span>  
 <span data-ttu-id="121bd-116">强名称标记是公钥的用于存储在元数据中的密钥信息时节省空间的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="121bd-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="121bd-117">具体而言，强名称令牌将用于程序集引用来引用依赖程序集。</span><span class="sxs-lookup"><span data-stu-id="121bd-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="121bd-118">要求</span><span class="sxs-lookup"><span data-stu-id="121bd-118">Requirements</span></span>  
 <span data-ttu-id="121bd-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="121bd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="121bd-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="121bd-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="121bd-121">**库：** 作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="121bd-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="121bd-122">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="121bd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="121bd-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="121bd-123">See Also</span></span>  
 [<span data-ttu-id="121bd-124">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="121bd-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="121bd-125">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="121bd-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="121bd-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="121bd-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
