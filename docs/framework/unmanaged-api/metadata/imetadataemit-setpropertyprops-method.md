---
title: "IMetaDataEmit::SetPropertyProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fe79846b9fd576941c706b48a7aed0667c264a3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="75009-102">IMetaDataEmit::SetPropertyProps 方法</span><span class="sxs-lookup"><span data-stu-id="75009-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="75009-103">设置存储在通过调用定义的属性的元数据的功能[DefineProperty 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)。</span><span class="sxs-lookup"><span data-stu-id="75009-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75009-104">语法</span><span class="sxs-lookup"><span data-stu-id="75009-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="75009-105">参数</span><span class="sxs-lookup"><span data-stu-id="75009-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="75009-106">[in]要更改的属性标记</span><span class="sxs-lookup"><span data-stu-id="75009-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="75009-107">[in]属性的标志。</span><span class="sxs-lookup"><span data-stu-id="75009-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="75009-108">[in]属性的默认值的类型。</span><span class="sxs-lookup"><span data-stu-id="75009-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="75009-109">[in]属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="75009-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="75009-110">[in]中的字符 (Unicode) 的计数`pValue`。</span><span class="sxs-lookup"><span data-stu-id="75009-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="75009-111">[in]用于设置属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="75009-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="75009-112">[in]获取属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="75009-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="75009-113">[in]与属性关联的其他方法的数组。</span><span class="sxs-lookup"><span data-stu-id="75009-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="75009-114">终止与此数组`mdTokenNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="75009-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75009-115">要求</span><span class="sxs-lookup"><span data-stu-id="75009-115">Requirements</span></span>  
 <span data-ttu-id="75009-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75009-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75009-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75009-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75009-118">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="75009-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75009-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75009-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75009-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75009-120">See Also</span></span>  
 [<span data-ttu-id="75009-121">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="75009-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="75009-122">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="75009-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
