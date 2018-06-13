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
ms.openlocfilehash: 53ed486a885514d02bf2be9c473e102c2c5f0e15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446838"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="86daa-102">IMetaDataImport::EnumTypeDefs 方法</span><span class="sxs-lookup"><span data-stu-id="86daa-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="86daa-103">枚举表示当前范围内的所有类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="86daa-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86daa-104">语法</span><span class="sxs-lookup"><span data-stu-id="86daa-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86daa-105">参数</span><span class="sxs-lookup"><span data-stu-id="86daa-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="86daa-106">[out]新的枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="86daa-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="86daa-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="86daa-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="86daa-108">[in]用于存储 TypeDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="86daa-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="86daa-109">[in] `rTypeDefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="86daa-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="86daa-110">[out]在中返回的 TypeDef 标记数`rTypeDefs`。</span><span class="sxs-lookup"><span data-stu-id="86daa-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86daa-111">返回值</span><span class="sxs-lookup"><span data-stu-id="86daa-111">Return Value</span></span>  
  
|<span data-ttu-id="86daa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86daa-112">HRESULT</span></span>|<span data-ttu-id="86daa-113">描述</span><span class="sxs-lookup"><span data-stu-id="86daa-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="86daa-114">`EnumTypeDefs` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="86daa-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="86daa-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="86daa-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="86daa-116">在这种情况下，`pcTypeDefs`为零。</span><span class="sxs-lookup"><span data-stu-id="86daa-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86daa-117">备注</span><span class="sxs-lookup"><span data-stu-id="86daa-117">Remarks</span></span>  
 <span data-ttu-id="86daa-118">的 TypeDef 标记表示的类型，例如类或接口，以及通过一种扩展机制添加任何类型。</span><span class="sxs-lookup"><span data-stu-id="86daa-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86daa-119">要求</span><span class="sxs-lookup"><span data-stu-id="86daa-119">Requirements</span></span>  
 <span data-ttu-id="86daa-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86daa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86daa-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86daa-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86daa-122">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="86daa-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86daa-123">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86daa-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86daa-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="86daa-124">See Also</span></span>  
 [<span data-ttu-id="86daa-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="86daa-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="86daa-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="86daa-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
