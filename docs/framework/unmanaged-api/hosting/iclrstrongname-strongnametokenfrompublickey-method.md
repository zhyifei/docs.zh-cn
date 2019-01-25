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
ms.openlocfilehash: 62a5b8aa573938b8c1a218e52590f44d8dd26aae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715059"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="ae067-102">ICLRStrongName::StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="ae067-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="ae067-103">获取表示公钥的标记。</span><span class="sxs-lookup"><span data-stu-id="ae067-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="ae067-104">强名称标记是简写形式的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="ae067-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae067-105">语法</span><span class="sxs-lookup"><span data-stu-id="ae067-105">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae067-106">参数</span><span class="sxs-lookup"><span data-stu-id="ae067-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="ae067-107">[in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) ，其中包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="ae067-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="ae067-108">[in]大小，以字节为单位的`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="ae067-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="ae067-109">[out]中的键相对应的强名称令牌传递`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="ae067-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="ae067-110">公共语言运行时分配的内存用于返回令牌。</span><span class="sxs-lookup"><span data-stu-id="ae067-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="ae067-111">调用方必须释放此内存通过使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ae067-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="ae067-112">[out]以字节为单位，返回的强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="ae067-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae067-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ae067-113">Return Value</span></span>  
 <span data-ttu-id="ae067-114">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="ae067-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae067-115">备注</span><span class="sxs-lookup"><span data-stu-id="ae067-115">Remarks</span></span>  
 <span data-ttu-id="ae067-116">强名称标记是用于在元数据中存储密钥信息时节省空间的公共密钥使用缩写形式。</span><span class="sxs-lookup"><span data-stu-id="ae067-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="ae067-117">具体而言，强名称标记用于程序集引用中对依赖程序集，请参阅。</span><span class="sxs-lookup"><span data-stu-id="ae067-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae067-118">要求</span><span class="sxs-lookup"><span data-stu-id="ae067-118">Requirements</span></span>  
 <span data-ttu-id="ae067-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae067-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae067-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ae067-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ae067-121">**库：** 包含为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ae067-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="ae067-122">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae067-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae067-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae067-123">See also</span></span>
- [<span data-ttu-id="ae067-124">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="ae067-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="ae067-125">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="ae067-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="ae067-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="ae067-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
