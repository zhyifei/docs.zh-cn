---
title: "IMetaDataImport::GetPropertyProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc3a1ce1d07bda50b2b578e7d20870324d60edc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="3be7b-102">IMetaDataImport::GetPropertyProps 方法</span><span class="sxs-lookup"><span data-stu-id="3be7b-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="3be7b-103">获取指定标记所表示的属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="3be7b-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3be7b-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3be7b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3be7b-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="3be7b-106">[in]一个表示要返回的元数据的属性的令牌。</span><span class="sxs-lookup"><span data-stu-id="3be7b-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="3be7b-107">[out]指向表示实现属性的类型的 TypeDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3be7b-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="3be7b-108">[out]一个缓冲区来容纳属性名。</span><span class="sxs-lookup"><span data-stu-id="3be7b-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="3be7b-109">[in]在宽字符为单位的大小`szProperty`。</span><span class="sxs-lookup"><span data-stu-id="3be7b-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="3be7b-110">[out]在中返回的宽字符数`szProperty`。</span><span class="sxs-lookup"><span data-stu-id="3be7b-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="3be7b-111">[out]指向向属性应用任何属性标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3be7b-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="3be7b-112">此值是从一个位掩码[CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="3be7b-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="3be7b-113">[out]指向该属性的元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="3be7b-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="3be7b-114">[out]在返回的字节数`ppvSig`。</span><span class="sxs-lookup"><span data-stu-id="3be7b-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="3be7b-115">[out]一个标志，指定的类型是属性的默认值的常数。</span><span class="sxs-lookup"><span data-stu-id="3be7b-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="3be7b-116">此值是从 CorElementType 枚举。</span><span class="sxs-lookup"><span data-stu-id="3be7b-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="3be7b-117">[out]指向将存储此属性的默认值的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="3be7b-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="3be7b-118">[out]在宽字符为单位的大小`ppDefaultValue`，如果`pdwCPlusTypeFlag`是 ELEMENT_TYPE_STRING; 否则，此值不相关。</span><span class="sxs-lookup"><span data-stu-id="3be7b-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="3be7b-119">在这种情况下的长度`ppDefaultValue`从指定的类型推断`pdwCPlusTypeFlag`。</span><span class="sxs-lookup"><span data-stu-id="3be7b-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="3be7b-120">[out]指向在表示属性 set 访问器方法的 MethodDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3be7b-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="3be7b-121">[out]指向在表示该属性的 get 访问器方法的 MethodDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3be7b-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="3be7b-122">[out]表示与属性关联的其他方法的 MethodDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="3be7b-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3be7b-123">[in] `rmdOtherMethod` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="3be7b-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="3be7b-124">如果未提供足够大以保存所有方法的数组，它们会跳过而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="3be7b-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="3be7b-125">[out]在中返回的 MethodDef 标记数`rmdOtherMethod`。</span><span class="sxs-lookup"><span data-stu-id="3be7b-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3be7b-126">要求</span><span class="sxs-lookup"><span data-stu-id="3be7b-126">Requirements</span></span>  
 <span data-ttu-id="3be7b-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3be7b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3be7b-128">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3be7b-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3be7b-129">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3be7b-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3be7b-130">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3be7b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be7b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3be7b-131">See Also</span></span>  
 [<span data-ttu-id="3be7b-132">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3be7b-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3be7b-133">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3be7b-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
