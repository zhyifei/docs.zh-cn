---
title: IMetaDataEmit::DefineCustomAttribute 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a11e9919dc1338c4b67c3c4b0f082e330c29d9eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445077"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="27974-102">IMetaDataEmit::DefineCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="27974-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="27974-103">使用指定的元数据签名，要附加到指定的对象，创建的自定义特性的定义并获取指向该自定义特性定义的标记。</span><span class="sxs-lookup"><span data-stu-id="27974-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27974-104">语法</span><span class="sxs-lookup"><span data-stu-id="27974-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27974-105">参数</span><span class="sxs-lookup"><span data-stu-id="27974-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="27974-106">[in]所有者项标记。</span><span class="sxs-lookup"><span data-stu-id="27974-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="27974-107">[in]标识自定义特性的标记。</span><span class="sxs-lookup"><span data-stu-id="27974-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="27974-108">[in]指向自定义特性的指针。</span><span class="sxs-lookup"><span data-stu-id="27974-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="27974-109">[in]中的字节计数`pCustomAttribute`。</span><span class="sxs-lookup"><span data-stu-id="27974-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="27974-110">[out]`mdCustomAttribute`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="27974-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27974-111">要求</span><span class="sxs-lookup"><span data-stu-id="27974-111">Requirements</span></span>  
 <span data-ttu-id="27974-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27974-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27974-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27974-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27974-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="27974-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27974-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27974-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27974-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="27974-116">See Also</span></span>  
 [<span data-ttu-id="27974-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="27974-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="27974-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="27974-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
