---
title: IMetaDataImport::GetPropertyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175325"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="a4845-102">IMetaDataImport::GetPropertyProps 方法</span><span class="sxs-lookup"><span data-stu-id="a4845-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="a4845-103">获取指定令牌表示的属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="a4845-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4845-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4845-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="a4845-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a4845-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="a4845-106">[在]表示要为其返回元数据的属性的令牌。</span><span class="sxs-lookup"><span data-stu-id="a4845-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="a4845-107">[出]指向 TypeDef 令牌的指针，表示实现该属性的类型。</span><span class="sxs-lookup"><span data-stu-id="a4845-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="a4845-108">[出]保存属性名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="a4845-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="a4845-109">[在]以 宽字符表示`szProperty`的大小。</span><span class="sxs-lookup"><span data-stu-id="a4845-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="a4845-110">[出]在 中`szProperty`返回的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="a4845-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="a4845-111">[出]指向应用于该属性的任何属性标志的指针。</span><span class="sxs-lookup"><span data-stu-id="a4845-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="a4845-112">此值是[CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)枚举中的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a4845-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="a4845-113">[出]指向属性的元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="a4845-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="a4845-114">[出]在 中`ppvSig`返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="a4845-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="a4845-115">[出]指定作为属性默认值的常量类型的标志。</span><span class="sxs-lookup"><span data-stu-id="a4845-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="a4845-116">此值来自 CorElementType 枚举。</span><span class="sxs-lookup"><span data-stu-id="a4845-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="a4845-117">[出]指向存储此属性的默认值的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="a4845-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="a4845-118">[出]大字符的大小`ppDefaultValue`，如果`pdwCPlusTypeFlag`为ELEMENT_TYPE_STRING;否则，此值不相关。</span><span class="sxs-lookup"><span data-stu-id="a4845-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="a4845-119">在这种情况下，将从 指定的类型推断`ppDefaultValue`的长度`pdwCPlusTypeFlag`。</span><span class="sxs-lookup"><span data-stu-id="a4845-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="a4845-120">[出]指向 MethodDef 令牌的指针，表示属性的设置访问器方法。</span><span class="sxs-lookup"><span data-stu-id="a4845-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="a4845-121">[出]指向 MethodDef 令牌的指针，表示属性的 get 访问器方法。</span><span class="sxs-lookup"><span data-stu-id="a4845-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="a4845-122">[出]表示与属性关联的其他方法的 MethodDef 令牌数组。</span><span class="sxs-lookup"><span data-stu-id="a4845-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a4845-123">[in] `rmdOtherMethod` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a4845-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="a4845-124">如果提供的数组足够大以容纳所有方法，则不会发出警告即可跳过这些方法。</span><span class="sxs-lookup"><span data-stu-id="a4845-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="a4845-125">[出]在 中`rmdOtherMethod`返回的 MethodDef 令牌数。</span><span class="sxs-lookup"><span data-stu-id="a4845-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4845-126">要求</span><span class="sxs-lookup"><span data-stu-id="a4845-126">Requirements</span></span>  
 <span data-ttu-id="a4845-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4845-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4845-128">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a4845-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4845-129">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="a4845-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4845-130">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4845-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4845-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4845-131">See also</span></span>

- [<span data-ttu-id="a4845-132">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a4845-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a4845-133">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a4845-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
