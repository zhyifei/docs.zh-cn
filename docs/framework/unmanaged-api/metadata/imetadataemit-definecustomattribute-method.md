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
ms.openlocfilehash: 9c4ed282e259aa46fc0cb0175214dc51d3d5fbee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175884"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="b5add-102">IMetaDataEmit::DefineCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="b5add-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="b5add-103">为具有指定元数据签名的自定义属性创建要附加到指定对象的定义，并获取该自定义属性定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="b5add-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5add-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5add-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5add-105">parameters</span><span class="sxs-lookup"><span data-stu-id="b5add-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="b5add-106">[在]所有者项的令牌。</span><span class="sxs-lookup"><span data-stu-id="b5add-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="b5add-107">[在]标识自定义属性的令牌。</span><span class="sxs-lookup"><span data-stu-id="b5add-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="b5add-108">[在]指向自定义属性的指针。</span><span class="sxs-lookup"><span data-stu-id="b5add-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="b5add-109">[在]中的`pCustomAttribute`字节计数。</span><span class="sxs-lookup"><span data-stu-id="b5add-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="b5add-110">[出]分配的`mdCustomAttribute`令牌。</span><span class="sxs-lookup"><span data-stu-id="b5add-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5add-111">要求</span><span class="sxs-lookup"><span data-stu-id="b5add-111">Requirements</span></span>  
 <span data-ttu-id="b5add-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5add-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5add-113">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="b5add-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5add-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b5add-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5add-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5add-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5add-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5add-116">See also</span></span>

- [<span data-ttu-id="b5add-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="b5add-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b5add-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="b5add-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
