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
ms.openlocfilehash: 66186d25e8fee0d6b25c0a2069d46ff9a104c625
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450033"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="ddeb2-102">IMetaDataImport::EnumModuleRefs 方法</span><span class="sxs-lookup"><span data-stu-id="ddeb2-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="ddeb2-103">枚举表示导入的模块的 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddeb2-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddeb2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddeb2-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddeb2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ddeb2-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ddeb2-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="ddeb2-108">弄用于存储 ModuleRef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ddeb2-109">[in] `rModuleRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="ddeb2-110">弄`rModuleRefs`中返回的 ModuleRef 令牌数。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddeb2-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ddeb2-111">Return Value</span></span>  
  
|<span data-ttu-id="ddeb2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddeb2-112">HRESULT</span></span>|<span data-ttu-id="ddeb2-113">说明</span><span class="sxs-lookup"><span data-stu-id="ddeb2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ddeb2-114">`EnumModuleRefs` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ddeb2-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ddeb2-116">在这种情况下，`pcModuleRefs` 为零。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddeb2-117">要求</span><span class="sxs-lookup"><span data-stu-id="ddeb2-117">Requirements</span></span>  
 <span data-ttu-id="ddeb2-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddeb2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddeb2-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ddeb2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ddeb2-120">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ddeb2-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ddeb2-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddeb2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeb2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddeb2-122">See also</span></span>

- [<span data-ttu-id="ddeb2-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="ddeb2-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ddeb2-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="ddeb2-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
