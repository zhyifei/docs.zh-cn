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
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175780"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="8faa2-102">IMetaDataEmit::DefineProperty 方法</span><span class="sxs-lookup"><span data-stu-id="8faa2-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="8faa2-103">使用指定的`get`和方法`set`访问器为指定类型创建属性定义，并获取该属性定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="8faa2-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8faa2-104">语法</span><span class="sxs-lookup"><span data-stu-id="8faa2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="8faa2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="8faa2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="8faa2-106">[在]正在定义属性的类或接口的令牌。</span><span class="sxs-lookup"><span data-stu-id="8faa2-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="8faa2-107">[在]属性的名称。</span><span class="sxs-lookup"><span data-stu-id="8faa2-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="8faa2-108">[在]属性标志。</span><span class="sxs-lookup"><span data-stu-id="8faa2-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="8faa2-109">[在]属性签名。</span><span class="sxs-lookup"><span data-stu-id="8faa2-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="8faa2-110">[在]中的`pvSig`字节计数。</span><span class="sxs-lookup"><span data-stu-id="8faa2-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="8faa2-111">[在]属性的默认值的类型。</span><span class="sxs-lookup"><span data-stu-id="8faa2-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8faa2-112">[在]属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="8faa2-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="8faa2-113">[在]中的（Unicode） 字符的`pValue`计数。</span><span class="sxs-lookup"><span data-stu-id="8faa2-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="8faa2-114">[在]设置属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="8faa2-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="8faa2-115">[在]获取属性值的方法。</span><span class="sxs-lookup"><span data-stu-id="8faa2-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="8faa2-116">[在]与 属性关联的其他方法的数组。</span><span class="sxs-lookup"><span data-stu-id="8faa2-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="8faa2-117">使用 终止数组`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="8faa2-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="8faa2-118">[出]分配的`mdProperty`令牌。</span><span class="sxs-lookup"><span data-stu-id="8faa2-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8faa2-119">要求</span><span class="sxs-lookup"><span data-stu-id="8faa2-119">Requirements</span></span>  
 <span data-ttu-id="8faa2-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8faa2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8faa2-121">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="8faa2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8faa2-122">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8faa2-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8faa2-123">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8faa2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8faa2-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8faa2-124">See also</span></span>

- [<span data-ttu-id="8faa2-125">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="8faa2-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8faa2-126">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="8faa2-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
