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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6ed8bbbd9699fe707d638bb8d07064e508b6f2fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447767"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="1ab2e-102">IMetaDataImport::EnumFieldsWithName 方法</span><span class="sxs-lookup"><span data-stu-id="1ab2e-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="1ab2e-103">枚举具有指定名称的指定类型的 FieldDef 标记。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ab2e-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ab2e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ab2e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1ab2e-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="1ab2e-107">[in]要枚举其字段的类型的标记。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="1ab2e-108">[in]限制在枚举的作用域的字段名。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="1ab2e-109">[out]用于存储 FieldDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1ab2e-110">[in] `rFields` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1ab2e-111">[out]FieldDef 标记中返回的实际数目`rFields`。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab2e-112">备注</span><span class="sxs-lookup"><span data-stu-id="1ab2e-112">Remarks</span></span>  
 <span data-ttu-id="1ab2e-113">与不同[imetadataimport:: Enumfields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md)，`EnumFieldsWithName`放弃不具有指定的名称的所有字段令牌。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ab2e-114">返回值</span><span class="sxs-lookup"><span data-stu-id="1ab2e-114">Return Value</span></span>  
  
|<span data-ttu-id="1ab2e-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ab2e-115">HRESULT</span></span>|<span data-ttu-id="1ab2e-116">描述</span><span class="sxs-lookup"><span data-stu-id="1ab2e-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1ab2e-117">`EnumFieldsWithName` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1ab2e-118">没有要枚举的字段。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-118">There are no fields to enumerate.</span></span> <span data-ttu-id="1ab2e-119">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ab2e-120">要求</span><span class="sxs-lookup"><span data-stu-id="1ab2e-120">Requirements</span></span>  
 <span data-ttu-id="1ab2e-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ab2e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab2e-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1ab2e-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ab2e-123">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1ab2e-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ab2e-124">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab2e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab2e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ab2e-125">See Also</span></span>  
 [<span data-ttu-id="1ab2e-126">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="1ab2e-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1ab2e-127">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="1ab2e-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
