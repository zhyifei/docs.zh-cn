---
title: IMetaDataImport::EnumTypeSpecs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01151dc2fe6aa995285a34076527609816b2f3e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205155"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="7bd3d-102">IMetaDataImport::EnumTypeSpecs 方法</span><span class="sxs-lookup"><span data-stu-id="7bd3d-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="7bd3d-103">枚举当前元数据范围内定义的 TypeSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7bd3d-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bd3d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7bd3d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7bd3d-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7bd3d-107">对于首次调用此方法，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="7bd3d-108">[out]用于存储 TypeSpec 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7bd3d-109">[in] `rTypeSpecs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="7bd3d-110">[out]在中返回的 TypeSpec 标记数`rTypeSpecs`。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bd3d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7bd3d-111">Return Value</span></span>  
  
|<span data-ttu-id="7bd3d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7bd3d-112">HRESULT</span></span>|<span data-ttu-id="7bd3d-113">描述</span><span class="sxs-lookup"><span data-stu-id="7bd3d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7bd3d-114">`EnumTypeSpecs` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7bd3d-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7bd3d-116">在这种情况下，`pcTypeSpecs`为零。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bd3d-117">备注</span><span class="sxs-lookup"><span data-stu-id="7bd3d-117">Remarks</span></span>  
 <span data-ttu-id="7bd3d-118">TypeSpec 标记创建的[imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bd3d-119">要求</span><span class="sxs-lookup"><span data-stu-id="7bd3d-119">Requirements</span></span>  
 <span data-ttu-id="7bd3d-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd3d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bd3d-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7bd3d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7bd3d-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7bd3d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7bd3d-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd3d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd3d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7bd3d-124">See also</span></span>

- [<span data-ttu-id="7bd3d-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7bd3d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7bd3d-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7bd3d-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
