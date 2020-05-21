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
ms.openlocfilehash: e61a652072b424d1245518c832f9b0856e0f2021
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762599"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="01945-102">ICLRStrongName::StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="01945-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="01945-103">获取表示公钥的标记。</span><span class="sxs-lookup"><span data-stu-id="01945-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="01945-104">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="01945-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01945-105">语法</span><span class="sxs-lookup"><span data-stu-id="01945-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01945-106">参数</span><span class="sxs-lookup"><span data-stu-id="01945-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="01945-107">中[PublicKeyBlob](../strong-naming/publickeyblob-structure.md)类型的结构，它包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="01945-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="01945-108">中的大小（以字节为单位） `pbPublicKeyBlob` 。</span><span class="sxs-lookup"><span data-stu-id="01945-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="01945-109">弄与传入的密钥对应的强名称标记 `pbPublicKeyBlob` 。</span><span class="sxs-lookup"><span data-stu-id="01945-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="01945-110">公共语言运行时分配要在其中返回标记的内存。</span><span class="sxs-lookup"><span data-stu-id="01945-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="01945-111">调用方必须通过使用[ICLRStrongName：： StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md)方法释放此内存。</span><span class="sxs-lookup"><span data-stu-id="01945-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="01945-112">弄返回的强名称标记的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="01945-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01945-113">返回值</span><span class="sxs-lookup"><span data-stu-id="01945-113">Return Value</span></span>  
 <span data-ttu-id="01945-114">`S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="01945-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01945-115">注解</span><span class="sxs-lookup"><span data-stu-id="01945-115">Remarks</span></span>  
 <span data-ttu-id="01945-116">强名称标记是用于在元数据中存储密钥信息时节省空间的公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="01945-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="01945-117">具体而言，强名称令牌在程序集引用中用于引用依赖程序集。</span><span class="sxs-lookup"><span data-stu-id="01945-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01945-118">要求</span><span class="sxs-lookup"><span data-stu-id="01945-118">Requirements</span></span>  
 <span data-ttu-id="01945-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01945-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01945-120">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="01945-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="01945-121">**库：** 作为资源包括在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="01945-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="01945-122">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01945-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01945-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01945-123">See also</span></span>

- [<span data-ttu-id="01945-124">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="01945-124">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="01945-125">PublicKeyBlob 结构</span><span class="sxs-lookup"><span data-stu-id="01945-125">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="01945-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="01945-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
