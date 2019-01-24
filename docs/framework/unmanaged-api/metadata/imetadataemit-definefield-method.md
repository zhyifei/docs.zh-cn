---
title: IMetaDataEmit::DefineField 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dfe888f74face85179306c982f7b5a888752987e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742794"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="1cc64-102">IMetaDataEmit::DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="1cc64-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="1cc64-103">使用指定的元数据签名中，创建一个字段的定义并获取该字段定义的标记。</span><span class="sxs-lookup"><span data-stu-id="1cc64-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc64-104">语法</span><span class="sxs-lookup"><span data-stu-id="1cc64-104">Syntax</span></span>  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cc64-105">参数</span><span class="sxs-lookup"><span data-stu-id="1cc64-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1cc64-106">[in]`mdTypeDef`令牌对封闭类或接口。</span><span class="sxs-lookup"><span data-stu-id="1cc64-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="1cc64-107">[in]Unicode 中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="1cc64-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="1cc64-108">[in]字段特性。</span><span class="sxs-lookup"><span data-stu-id="1cc64-108">[in] The field attributes.</span></span> <span data-ttu-id="1cc64-109">这是一个位掩码的`CorFieldAttr`值。</span><span class="sxs-lookup"><span data-stu-id="1cc64-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1cc64-110">[in]作为 BLOB 字段签名。</span><span class="sxs-lookup"><span data-stu-id="1cc64-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1cc64-111">[in]中的字节计数`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="1cc64-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="1cc64-112">[in]`ELEMENT_TYPE_` *\** 的常量值。</span><span class="sxs-lookup"><span data-stu-id="1cc64-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="1cc64-113">这是`CorElementType`值。</span><span class="sxs-lookup"><span data-stu-id="1cc64-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="1cc64-114">如果不定义该字段的常数值，使用`ELEMENT_TYPE_END`。</span><span class="sxs-lookup"><span data-stu-id="1cc64-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="1cc64-115">[in]字段的常量值。</span><span class="sxs-lookup"><span data-stu-id="1cc64-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="1cc64-116">[in]\(Unicode) 字符中的大小`pValue`。</span><span class="sxs-lookup"><span data-stu-id="1cc64-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="1cc64-117">[out]`mdFieldDef`分配标记。</span><span class="sxs-lookup"><span data-stu-id="1cc64-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc64-118">要求</span><span class="sxs-lookup"><span data-stu-id="1cc64-118">Requirements</span></span>  
 <span data-ttu-id="1cc64-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc64-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc64-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1cc64-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1cc64-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1cc64-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cc64-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cc64-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc64-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cc64-123">See also</span></span>
- [<span data-ttu-id="1cc64-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="1cc64-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1cc64-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="1cc64-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
