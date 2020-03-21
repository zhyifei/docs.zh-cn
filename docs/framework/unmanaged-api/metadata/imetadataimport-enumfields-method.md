---
title: IMetaDataImport::EnumFields 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: be2845d1d660d86447cfbb6f2845a8e68b727e66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175507"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="13617-102">IMetaDataImport::EnumFields 方法</span><span class="sxs-lookup"><span data-stu-id="13617-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="13617-103">枚举指定的 TypeDef 标记所引用的类型的 FieldDef 标记。</span><span class="sxs-lookup"><span data-stu-id="13617-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13617-104">语法</span><span class="sxs-lookup"><span data-stu-id="13617-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13617-105">parameters</span><span class="sxs-lookup"><span data-stu-id="13617-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="13617-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="13617-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="13617-107">[在]要枚举其字段的类的 TypeDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="13617-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="13617-108">[出]FieldDef 令牌的列表。</span><span class="sxs-lookup"><span data-stu-id="13617-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="13617-109">[in] `rFields` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="13617-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="13617-110">[出]在 中`rFields`返回的实际字段Def 令牌数。</span><span class="sxs-lookup"><span data-stu-id="13617-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13617-111">返回值</span><span class="sxs-lookup"><span data-stu-id="13617-111">Return Value</span></span>  
  
|<span data-ttu-id="13617-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13617-112">HRESULT</span></span>|<span data-ttu-id="13617-113">说明</span><span class="sxs-lookup"><span data-stu-id="13617-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="13617-114">`EnumFields`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="13617-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="13617-115">没有要枚举的字段。</span><span class="sxs-lookup"><span data-stu-id="13617-115">There are no fields to enumerate.</span></span> <span data-ttu-id="13617-116">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="13617-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13617-117">要求</span><span class="sxs-lookup"><span data-stu-id="13617-117">Requirements</span></span>  
 <span data-ttu-id="13617-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13617-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13617-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="13617-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13617-120">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="13617-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13617-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13617-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13617-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13617-122">See also</span></span>

- [<span data-ttu-id="13617-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="13617-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="13617-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="13617-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
