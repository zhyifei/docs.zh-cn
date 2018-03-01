---
title: "IMetaDataEmit::DefineField 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e2c4b5604c3daec78744eb8902a30750571b9f82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="77000-102">IMetaDataEmit::DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="77000-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="77000-103">使用指定的元数据签名中，创建一个字段的定义并获取指向该字段定义的标记。</span><span class="sxs-lookup"><span data-stu-id="77000-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77000-104">语法</span><span class="sxs-lookup"><span data-stu-id="77000-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="77000-105">参数</span><span class="sxs-lookup"><span data-stu-id="77000-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="77000-106">[in]`mdTypeDef`令牌对封闭类或接口。</span><span class="sxs-lookup"><span data-stu-id="77000-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="77000-107">[in]Unicode 中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="77000-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="77000-108">[in]中的字段特性。</span><span class="sxs-lookup"><span data-stu-id="77000-108">[in] The field attributes.</span></span> <span data-ttu-id="77000-109">这是一个位掩码的`CorFieldAttr`值。</span><span class="sxs-lookup"><span data-stu-id="77000-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="77000-110">[in]作为 BLOB 的字段签名。</span><span class="sxs-lookup"><span data-stu-id="77000-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="77000-111">[in]中的字节计数`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="77000-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlage`  
 <span data-ttu-id="77000-112">[in]`ELEMENT_TYPE_`  *\** 的常量值。</span><span class="sxs-lookup"><span data-stu-id="77000-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="77000-113">这是`CorElementType`值。</span><span class="sxs-lookup"><span data-stu-id="77000-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="77000-114">如果不定义字段的常量值，使用`ELEMENT_TYPE_END`。</span><span class="sxs-lookup"><span data-stu-id="77000-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="77000-115">[in]字段的常量值。</span><span class="sxs-lookup"><span data-stu-id="77000-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="77000-116">[in]以 (Unicode) 字符为单位的大小`pValue`。</span><span class="sxs-lookup"><span data-stu-id="77000-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="77000-117">[out]`mdFieldDef`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="77000-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77000-118">惠?</span><span class="sxs-lookup"><span data-stu-id="77000-118">Requirements</span></span>  
 <span data-ttu-id="77000-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77000-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77000-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77000-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77000-121">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="77000-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77000-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77000-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77000-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="77000-123">See Also</span></span>  
 [<span data-ttu-id="77000-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="77000-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="77000-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="77000-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
