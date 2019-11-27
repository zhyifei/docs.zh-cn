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
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432555"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="4c203-102">IMetaDataEmit::DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="4c203-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="4c203-103">使用指定的元数据签名创建字段的定义，并获取该字段定义的标记。</span><span class="sxs-lookup"><span data-stu-id="4c203-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c203-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c203-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4c203-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c203-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4c203-106">中封闭类或接口的 `mdTypeDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="4c203-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="4c203-107">中Unicode 中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="4c203-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="4c203-108">中字段特性。</span><span class="sxs-lookup"><span data-stu-id="4c203-108">[in] The field attributes.</span></span> <span data-ttu-id="4c203-109">这是 `CorFieldAttr` 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="4c203-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4c203-110">中作为 BLOB 的字段签名。</span><span class="sxs-lookup"><span data-stu-id="4c203-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4c203-111">中`pvSigBlob`中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="4c203-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="4c203-112">中常量值的 `ELEMENT_TYPE_` *\** 。</span><span class="sxs-lookup"><span data-stu-id="4c203-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="4c203-113">这是 `CorElementType` 值。</span><span class="sxs-lookup"><span data-stu-id="4c203-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="4c203-114">如果没有为字段定义常数值，请使用 `ELEMENT_TYPE_END`。</span><span class="sxs-lookup"><span data-stu-id="4c203-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4c203-115">中字段的常数值。</span><span class="sxs-lookup"><span data-stu-id="4c203-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="4c203-116">中`pValue`的大小（Unicode）字符。</span><span class="sxs-lookup"><span data-stu-id="4c203-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="4c203-117">弄分配 `mdFieldDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="4c203-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c203-118">要求</span><span class="sxs-lookup"><span data-stu-id="4c203-118">Requirements</span></span>  
 <span data-ttu-id="4c203-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c203-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c203-120">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4c203-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c203-121">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4c203-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c203-122">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c203-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c203-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c203-123">See also</span></span>

- [<span data-ttu-id="4c203-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="4c203-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4c203-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="4c203-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
