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
ms.openlocfilehash: 7547d7557169b1279125141afb5b05e22341942a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432741"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="b0884-102">IMetaDataEmit2::DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="b0884-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="b0884-103">Creates a generic instance of a method, and gets a token to the definition.</span><span class="sxs-lookup"><span data-stu-id="b0884-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0884-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0884-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0884-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0884-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="b0884-106">[in] A token for the method of which to create the generic instance.</span><span class="sxs-lookup"><span data-stu-id="b0884-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="b0884-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="b0884-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b0884-108">[in] A pointer to the binary COM+ signature of the method.</span><span class="sxs-lookup"><span data-stu-id="b0884-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="b0884-109">[in] The size, in bytes, of `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="b0884-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="b0884-110">[out] A token to the metadata signature definition of the method.</span><span class="sxs-lookup"><span data-stu-id="b0884-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0884-111">要求</span><span class="sxs-lookup"><span data-stu-id="b0884-111">Requirements</span></span>  
 <span data-ttu-id="b0884-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0884-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0884-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b0884-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0884-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0884-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0884-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0884-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0884-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0884-116">See also</span></span>

- [<span data-ttu-id="b0884-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="b0884-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="b0884-118">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="b0884-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
