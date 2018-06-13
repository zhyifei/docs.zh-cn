---
title: IMetaDataEmit::DefineProperty 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c250a577f2ccdbbfefb35225b880c0e4317db36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448102"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="08d17-102">IMetaDataEmit::DefineProperty 方法</span><span class="sxs-lookup"><span data-stu-id="08d17-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="08d17-103">创建指定类型的属性定义具有指定`get`和`set`方法访问器中，并获取指向该属性定义的标记。</span><span class="sxs-lookup"><span data-stu-id="08d17-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08d17-104">语法</span><span class="sxs-lookup"><span data-stu-id="08d17-104">Syntax</span></span>  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08d17-105">参数</span><span class="sxs-lookup"><span data-stu-id="08d17-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="08d17-106">[in]为类或接口在其定义的属性标记。</span><span class="sxs-lookup"><span data-stu-id="08d17-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="08d17-107">[in]属性的名称。</span><span class="sxs-lookup"><span data-stu-id="08d17-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="08d17-108">[in]属性的标志。</span><span class="sxs-lookup"><span data-stu-id="08d17-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="08d17-109">[in]属性签名中。</span><span class="sxs-lookup"><span data-stu-id="08d17-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="08d17-110">[in]中的字节计数`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="08d17-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="08d17-111">[in]属性的默认值的类型。</span><span class="sxs-lookup"><span data-stu-id="08d17-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="08d17-112">[in]属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="08d17-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="08d17-113">[in]中的字符 (Unicode) 的计数`pValue`。</span><span class="sxs-lookup"><span data-stu-id="08d17-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="08d17-114">[in]用于设置属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="08d17-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="08d17-115">[in]获取属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="08d17-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="08d17-116">[in]与属性关联的其他方法的数组。</span><span class="sxs-lookup"><span data-stu-id="08d17-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="08d17-117">终止与数组`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="08d17-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="08d17-118">[out]`mdProperty`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="08d17-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08d17-119">要求</span><span class="sxs-lookup"><span data-stu-id="08d17-119">Requirements</span></span>  
 <span data-ttu-id="08d17-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08d17-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08d17-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="08d17-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08d17-122">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="08d17-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08d17-123">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08d17-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d17-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="08d17-124">See Also</span></span>  
 [<span data-ttu-id="08d17-125">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="08d17-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="08d17-126">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="08d17-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
