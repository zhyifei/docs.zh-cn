---
title: IMetaDataImport::EnumTypeDefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a285543571c843a982b6615fdc4b5f1325ed066
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466955"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="a8b58-102">IMetaDataImport::EnumTypeDefs 方法</span><span class="sxs-lookup"><span data-stu-id="a8b58-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="a8b58-103">枚举表示当前范围内的所有类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="a8b58-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b58-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8b58-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8b58-105">参数</span><span class="sxs-lookup"><span data-stu-id="a8b58-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a8b58-106">[out]指向新枚举数的指针。</span><span class="sxs-lookup"><span data-stu-id="a8b58-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="a8b58-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a8b58-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="a8b58-108">[in]用于存储 TypeDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="a8b58-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a8b58-109">[in] `rTypeDefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a8b58-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="a8b58-110">[out]在中返回的 TypeDef 标记数`rTypeDefs`。</span><span class="sxs-lookup"><span data-stu-id="a8b58-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8b58-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a8b58-111">Return Value</span></span>  
  
|<span data-ttu-id="a8b58-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8b58-112">HRESULT</span></span>|<span data-ttu-id="a8b58-113">描述</span><span class="sxs-lookup"><span data-stu-id="a8b58-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a8b58-114">`EnumTypeDefs` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a8b58-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a8b58-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="a8b58-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a8b58-116">在这种情况下，`pcTypeDefs`为零。</span><span class="sxs-lookup"><span data-stu-id="a8b58-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8b58-117">备注</span><span class="sxs-lookup"><span data-stu-id="a8b58-117">Remarks</span></span>  
 <span data-ttu-id="a8b58-118">TypeDef 标记表示一个类或接口，如类型以及可扩展性机制通过添加任何类型。</span><span class="sxs-lookup"><span data-stu-id="a8b58-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8b58-119">要求</span><span class="sxs-lookup"><span data-stu-id="a8b58-119">Requirements</span></span>  
 <span data-ttu-id="a8b58-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8b58-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8b58-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8b58-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8b58-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a8b58-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8b58-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8b58-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b58-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b58-124">See also</span></span>
- [<span data-ttu-id="a8b58-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a8b58-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a8b58-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a8b58-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
