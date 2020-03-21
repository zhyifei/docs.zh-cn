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
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177703"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="9af30-102">IMetaDataEmit::DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="9af30-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="9af30-103">为具有指定元数据签名的字段创建定义，并获取该字段定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="9af30-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9af30-104">语法</span><span class="sxs-lookup"><span data-stu-id="9af30-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="9af30-105">parameters</span><span class="sxs-lookup"><span data-stu-id="9af30-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9af30-106">[在]封闭`mdTypeDef`类或接口的令牌。</span><span class="sxs-lookup"><span data-stu-id="9af30-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="9af30-107">[在]Unicode 中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="9af30-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="9af30-108">[在]字段属性。</span><span class="sxs-lookup"><span data-stu-id="9af30-108">[in] The field attributes.</span></span> <span data-ttu-id="9af30-109">这是值的`CorFieldAttr`位掩码。</span><span class="sxs-lookup"><span data-stu-id="9af30-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9af30-110">[在]字段签名作为 BLOB。</span><span class="sxs-lookup"><span data-stu-id="9af30-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9af30-111">[在]中的`pvSigBlob`字节计数。</span><span class="sxs-lookup"><span data-stu-id="9af30-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="9af30-112">[在]常`ELEMENT_TYPE_`*\** 量值的 。</span><span class="sxs-lookup"><span data-stu-id="9af30-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="9af30-113">这是一个`CorElementType`值。</span><span class="sxs-lookup"><span data-stu-id="9af30-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="9af30-114">如果未为字段定义常量值，请使用`ELEMENT_TYPE_END`。</span><span class="sxs-lookup"><span data-stu-id="9af30-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="9af30-115">[在]字段的常量值。</span><span class="sxs-lookup"><span data-stu-id="9af30-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="9af30-116">[在]的大小（Unicode）字符。 `pValue`</span><span class="sxs-lookup"><span data-stu-id="9af30-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="9af30-117">[出]分配的`mdFieldDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="9af30-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9af30-118">要求</span><span class="sxs-lookup"><span data-stu-id="9af30-118">Requirements</span></span>  
 <span data-ttu-id="9af30-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9af30-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9af30-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="9af30-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9af30-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9af30-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9af30-122">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9af30-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af30-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9af30-123">See also</span></span>

- [<span data-ttu-id="9af30-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="9af30-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9af30-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="9af30-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
