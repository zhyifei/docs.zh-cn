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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce6df232f3793b8b61d9fa7c18c9c90ca9fa3900
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184712"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="2b9a4-102">IMetaDataEmit2::DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="2b9a4-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="2b9a4-103">创建一个方法的泛型实例并获取定义的标记。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b9a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b9a4-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b9a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b9a4-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="2b9a4-106">[in]要创建泛型实例的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="2b9a4-107">该标记必须为类型`mdMethodDef`或`mdMemberRef`。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2b9a4-108">[in]指向二进制 COM + 方法的签名的指针。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="2b9a4-109">[in]大小，以字节为单位的`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="2b9a4-110">[out]该方法的元数据签名定义标记。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b9a4-111">要求</span><span class="sxs-lookup"><span data-stu-id="2b9a4-111">Requirements</span></span>  
 <span data-ttu-id="2b9a4-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b9a4-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b9a4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b9a4-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2b9a4-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2b9a4-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2b9a4-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b9a4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b9a4-116">See also</span></span>

- [<span data-ttu-id="2b9a4-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="2b9a4-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2b9a4-118">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="2b9a4-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
