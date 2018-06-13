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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd8a2d373b801bd8238d50eecb388ef511bc34bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446197"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="56000-102">IMetaDataImport::EnumFields 方法</span><span class="sxs-lookup"><span data-stu-id="56000-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="56000-103">枚举指定的 TypeDef 标记所引用的类型的 FieldDef 标记。</span><span class="sxs-lookup"><span data-stu-id="56000-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56000-104">语法</span><span class="sxs-lookup"><span data-stu-id="56000-104">Syntax</span></span>  
  
```  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56000-105">参数</span><span class="sxs-lookup"><span data-stu-id="56000-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="56000-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="56000-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="56000-107">[in]其字段都要枚举类的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="56000-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="56000-108">[out]FieldDef 标记列表。</span><span class="sxs-lookup"><span data-stu-id="56000-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="56000-109">[in] `rFields` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="56000-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="56000-110">[out]FieldDef 标记中返回的实际数目`rFields`。</span><span class="sxs-lookup"><span data-stu-id="56000-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56000-111">返回值</span><span class="sxs-lookup"><span data-stu-id="56000-111">Return Value</span></span>  
  
|<span data-ttu-id="56000-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56000-112">HRESULT</span></span>|<span data-ttu-id="56000-113">描述</span><span class="sxs-lookup"><span data-stu-id="56000-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="56000-114">`EnumFields` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="56000-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="56000-115">没有要枚举的字段。</span><span class="sxs-lookup"><span data-stu-id="56000-115">There are no fields to enumerate.</span></span> <span data-ttu-id="56000-116">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="56000-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56000-117">要求</span><span class="sxs-lookup"><span data-stu-id="56000-117">Requirements</span></span>  
 <span data-ttu-id="56000-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56000-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56000-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="56000-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56000-120">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="56000-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="56000-121">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56000-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56000-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="56000-122">See Also</span></span>  
 [<span data-ttu-id="56000-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="56000-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="56000-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="56000-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
