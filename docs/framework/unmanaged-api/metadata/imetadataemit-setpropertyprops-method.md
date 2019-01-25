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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 997e43e6a8be1ac2859e7338751272f3074be11d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523125"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="35f0f-102">IMetaDataEmit::SetPropertyProps 方法</span><span class="sxs-lookup"><span data-stu-id="35f0f-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="35f0f-103">设置存储在由调用之前定义属性的元数据中的功能[DefineProperty 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)。</span><span class="sxs-lookup"><span data-stu-id="35f0f-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35f0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="35f0f-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="35f0f-105">参数</span><span class="sxs-lookup"><span data-stu-id="35f0f-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="35f0f-106">[in]若要更改属性的标记</span><span class="sxs-lookup"><span data-stu-id="35f0f-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="35f0f-107">[in]属性的标志。</span><span class="sxs-lookup"><span data-stu-id="35f0f-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="35f0f-108">[in]该属性的默认值的类型。</span><span class="sxs-lookup"><span data-stu-id="35f0f-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="35f0f-109">[in]属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="35f0f-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="35f0f-110">[in]中的字符 (Unicode) 的计数`pValue`。</span><span class="sxs-lookup"><span data-stu-id="35f0f-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="35f0f-111">[in]用于设置属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="35f0f-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="35f0f-112">[in]获取属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="35f0f-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="35f0f-113">[in]与属性关联的其他方法的数组。</span><span class="sxs-lookup"><span data-stu-id="35f0f-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="35f0f-114">终止与此数组`mdTokenNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="35f0f-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35f0f-115">要求</span><span class="sxs-lookup"><span data-stu-id="35f0f-115">Requirements</span></span>  
 <span data-ttu-id="35f0f-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35f0f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35f0f-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35f0f-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35f0f-118">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="35f0f-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35f0f-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35f0f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f0f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="35f0f-120">See also</span></span>
- [<span data-ttu-id="35f0f-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="35f0f-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="35f0f-122">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="35f0f-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
