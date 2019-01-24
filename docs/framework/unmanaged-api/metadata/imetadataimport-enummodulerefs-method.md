---
title: IMetaDataImport::EnumModuleRefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e84581a0642fe5bee3b88b6774ab2155fd2736a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490779"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="4db77-102">IMetaDataImport::EnumModuleRefs 方法</span><span class="sxs-lookup"><span data-stu-id="4db77-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="4db77-103">枚举表示导入的模块的 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="4db77-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db77-104">语法</span><span class="sxs-lookup"><span data-stu-id="4db77-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4db77-105">参数</span><span class="sxs-lookup"><span data-stu-id="4db77-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4db77-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="4db77-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4db77-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4db77-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="4db77-108">[out]用于存储的 ModuleRef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="4db77-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4db77-109">[in] `rModuleRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4db77-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="4db77-110">[out]在中返回的 ModuleRef 标记数`rModuleRefs`。</span><span class="sxs-lookup"><span data-stu-id="4db77-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4db77-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4db77-111">Return Value</span></span>  
  
|<span data-ttu-id="4db77-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4db77-112">HRESULT</span></span>|<span data-ttu-id="4db77-113">描述</span><span class="sxs-lookup"><span data-stu-id="4db77-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4db77-114">`EnumModuleRefs` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4db77-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4db77-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="4db77-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4db77-116">在这种情况下，`pcModuleRefs`为零。</span><span class="sxs-lookup"><span data-stu-id="4db77-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4db77-117">要求</span><span class="sxs-lookup"><span data-stu-id="4db77-117">Requirements</span></span>  
 <span data-ttu-id="4db77-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4db77-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4db77-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4db77-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4db77-120">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4db77-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4db77-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4db77-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db77-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4db77-122">See also</span></span>
- [<span data-ttu-id="4db77-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4db77-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4db77-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4db77-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
