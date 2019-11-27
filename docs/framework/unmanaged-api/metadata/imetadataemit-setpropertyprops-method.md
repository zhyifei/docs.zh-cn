---
title: IMetaDataEmit::SetPropertyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: 0fdec87324d6efa0f911e37573093c19b93c0349
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440551"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="588bd-102">IMetaDataEmit::SetPropertyProps 方法</span><span class="sxs-lookup"><span data-stu-id="588bd-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="588bd-103">设置由之前调用[DefineProperty 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)定义的属性的元数据中存储的功能。</span><span class="sxs-lookup"><span data-stu-id="588bd-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="588bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="588bd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="588bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="588bd-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="588bd-106">中要更改的属性的标记</span><span class="sxs-lookup"><span data-stu-id="588bd-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="588bd-107">中属性标志。</span><span class="sxs-lookup"><span data-stu-id="588bd-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="588bd-108">中属性的默认值的类型。</span><span class="sxs-lookup"><span data-stu-id="588bd-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="588bd-109">中属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="588bd-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="588bd-110">中`pValue`中的（Unicode）字符的计数。</span><span class="sxs-lookup"><span data-stu-id="588bd-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="588bd-111">中用于设置属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="588bd-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="588bd-112">中获取属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="588bd-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="588bd-113">中与属性关联的其他方法的数组。</span><span class="sxs-lookup"><span data-stu-id="588bd-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="588bd-114">使用 `mdTokenNil` 标记终止此数组。</span><span class="sxs-lookup"><span data-stu-id="588bd-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="588bd-115">要求</span><span class="sxs-lookup"><span data-stu-id="588bd-115">Requirements</span></span>  
 <span data-ttu-id="588bd-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="588bd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="588bd-117">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="588bd-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="588bd-118">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="588bd-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="588bd-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="588bd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="588bd-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="588bd-120">See also</span></span>

- [<span data-ttu-id="588bd-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="588bd-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="588bd-122">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="588bd-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
