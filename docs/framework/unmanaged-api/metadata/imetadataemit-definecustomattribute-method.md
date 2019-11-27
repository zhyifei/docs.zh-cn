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
ms.openlocfilehash: e6a732b98ae02ba2b273b45921b7de61ab4fd29f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432635"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="d41e4-102">IMetaDataEmit::DefineCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="d41e4-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="d41e4-103">使用指定的元数据签名创建要附加到指定对象的自定义属性的定义，并获取该自定义属性定义的标记。</span><span class="sxs-lookup"><span data-stu-id="d41e4-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d41e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="d41e4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d41e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="d41e4-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="d41e4-106">中所有者项的标记。</span><span class="sxs-lookup"><span data-stu-id="d41e4-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="d41e4-107">中标识自定义属性的标记。</span><span class="sxs-lookup"><span data-stu-id="d41e4-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="d41e4-108">中指向自定义属性的指针。</span><span class="sxs-lookup"><span data-stu-id="d41e4-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="d41e4-109">中`pCustomAttribute`中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="d41e4-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="d41e4-110">弄分配 `mdCustomAttribute` 标记。</span><span class="sxs-lookup"><span data-stu-id="d41e4-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d41e4-111">要求</span><span class="sxs-lookup"><span data-stu-id="d41e4-111">Requirements</span></span>  
 <span data-ttu-id="d41e4-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d41e4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d41e4-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="d41e4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d41e4-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d41e4-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d41e4-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d41e4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41e4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d41e4-116">See also</span></span>

- [<span data-ttu-id="d41e4-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="d41e4-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d41e4-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="d41e4-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
