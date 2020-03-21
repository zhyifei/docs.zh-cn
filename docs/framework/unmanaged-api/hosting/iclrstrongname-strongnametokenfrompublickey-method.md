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
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176313"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="7abbd-102">ICLRStrongName::StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="7abbd-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="7abbd-103">获取表示公钥的令牌。</span><span class="sxs-lookup"><span data-stu-id="7abbd-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="7abbd-104">强名称令牌是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="7abbd-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7abbd-105">语法</span><span class="sxs-lookup"><span data-stu-id="7abbd-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7abbd-106">parameters</span><span class="sxs-lookup"><span data-stu-id="7abbd-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="7abbd-107">[在][公共密钥Blob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)类型的结构，其中包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="7abbd-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="7abbd-108">[在]的大小（以字节为单位）的大小`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="7abbd-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="7abbd-109">[出]与传入的键对应的强名称令牌`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="7abbd-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="7abbd-110">通用语言运行时分配要返回令牌的内存。</span><span class="sxs-lookup"><span data-stu-id="7abbd-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="7abbd-111">调用方必须使用[ICLRStrongNameName：：StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放此内存。</span><span class="sxs-lookup"><span data-stu-id="7abbd-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="7abbd-112">[出]返回的强名称令牌的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7abbd-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7abbd-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7abbd-113">Return Value</span></span>  
 <span data-ttu-id="7abbd-114">`S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="7abbd-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7abbd-115">备注</span><span class="sxs-lookup"><span data-stu-id="7abbd-115">Remarks</span></span>  
 <span data-ttu-id="7abbd-116">强名称令牌是公钥的缩短形式，用于在元数据中存储关键信息时节省空间。</span><span class="sxs-lookup"><span data-stu-id="7abbd-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="7abbd-117">具体而言，强名称令牌用于程序集引用以引用从属程序集。</span><span class="sxs-lookup"><span data-stu-id="7abbd-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7abbd-118">要求</span><span class="sxs-lookup"><span data-stu-id="7abbd-118">Requirements</span></span>  
 <span data-ttu-id="7abbd-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7abbd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7abbd-120">**标题：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7abbd-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7abbd-121">**库：** 作为资源包含在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7abbd-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="7abbd-122">**.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7abbd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abbd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7abbd-123">See also</span></span>

- [<span data-ttu-id="7abbd-124">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="7abbd-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="7abbd-125">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="7abbd-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="7abbd-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7abbd-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
