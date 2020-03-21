---
title: IMetaDataEmit2::DefineMethodSpec 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: a5d9342b8bfe650106ccf9daf2a91dfbcd575446
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175533"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="cd9f2-102">IMetaDataEmit2::DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="cd9f2-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="cd9f2-103">创建方法的泛型实例，并获取定义中的令牌。</span><span class="sxs-lookup"><span data-stu-id="cd9f2-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd9f2-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd9f2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="cd9f2-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="cd9f2-106">[在]用于创建泛型实例的方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="cd9f2-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="cd9f2-107">令牌必须为 类型`mdMethodDef`或`mdMemberRef`。</span><span class="sxs-lookup"><span data-stu-id="cd9f2-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="cd9f2-108">[在]指向方法的二进制 COM+ 签名的指针。</span><span class="sxs-lookup"><span data-stu-id="cd9f2-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="cd9f2-109">[在]的大小（以字节为单位）的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="cd9f2-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="cd9f2-110">[出]方法的元数据签名定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="cd9f2-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd9f2-111">要求</span><span class="sxs-lookup"><span data-stu-id="cd9f2-111">Requirements</span></span>  
 <span data-ttu-id="cd9f2-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd9f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd9f2-113">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="cd9f2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd9f2-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cd9f2-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd9f2-115">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd9f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9f2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd9f2-116">See also</span></span>

- [<span data-ttu-id="cd9f2-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="cd9f2-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="cd9f2-118">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="cd9f2-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
