---
title: IMetaDataImport::EnumFieldsWithName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
ms.openlocfilehash: bb8b531a884c9d3c2f33aa4aec5c4dbeaafe2b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177341"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="a9089-102">IMetaDataImport::EnumFieldsWithName 方法</span><span class="sxs-lookup"><span data-stu-id="a9089-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="a9089-103">枚举具有指定名称的指定类型的 FieldDef 标记。</span><span class="sxs-lookup"><span data-stu-id="a9089-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9089-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9089-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9089-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a9089-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a9089-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="a9089-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="a9089-107">[在]要枚举其字段的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="a9089-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="a9089-108">[在]限制枚举范围的字段名称。</span><span class="sxs-lookup"><span data-stu-id="a9089-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="a9089-109">[出]用于存储 FieldDef 令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="a9089-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a9089-110">[in] `rFields` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a9089-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a9089-111">[出]在 中`rFields`返回的实际字段Def 令牌数。</span><span class="sxs-lookup"><span data-stu-id="a9089-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9089-112">备注</span><span class="sxs-lookup"><span data-stu-id="a9089-112">Remarks</span></span>  
 <span data-ttu-id="a9089-113">与[IMetaDataImport：：enumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md)不同，`EnumFieldsWithName`则丢弃所有没有指定名称的字段令牌。</span><span class="sxs-lookup"><span data-stu-id="a9089-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9089-114">返回值</span><span class="sxs-lookup"><span data-stu-id="a9089-114">Return Value</span></span>  
  
|<span data-ttu-id="a9089-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9089-115">HRESULT</span></span>|<span data-ttu-id="a9089-116">说明</span><span class="sxs-lookup"><span data-stu-id="a9089-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a9089-117">`EnumFieldsWithName`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a9089-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a9089-118">没有要枚举的字段。</span><span class="sxs-lookup"><span data-stu-id="a9089-118">There are no fields to enumerate.</span></span> <span data-ttu-id="a9089-119">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="a9089-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9089-120">要求</span><span class="sxs-lookup"><span data-stu-id="a9089-120">Requirements</span></span>  
 <span data-ttu-id="a9089-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9089-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9089-122">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a9089-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9089-123">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="a9089-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9089-124">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9089-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9089-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9089-125">See also</span></span>

- [<span data-ttu-id="a9089-126">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a9089-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a9089-127">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a9089-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
