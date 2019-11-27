---
title: IMetaDataAssemblyImport::EnumAssemblyRefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 06b81615565a04db7d6cfef4da9b5372a85afd68
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450343"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="bd480-102">IMetaDataAssemblyImport::EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="bd480-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="bd480-103">枚举程序集清单中定义的 `mdAssemblyRef` 实例。</span><span class="sxs-lookup"><span data-stu-id="bd480-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd480-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd480-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd480-105">参数</span><span class="sxs-lookup"><span data-stu-id="bd480-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bd480-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="bd480-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bd480-107">当首次调用 `EnumAssemblyRefs` 方法时，此值必须为 null 值。</span><span class="sxs-lookup"><span data-stu-id="bd480-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="bd480-108">弄`mdAssemblyRef` 元数据标记的枚举。</span><span class="sxs-lookup"><span data-stu-id="bd480-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bd480-109">中可放置在 `rAssemblyRefs` 数组中的标记的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bd480-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bd480-110">弄实际置于 `rAssemblyRefs`中的标记数。</span><span class="sxs-lookup"><span data-stu-id="bd480-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd480-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bd480-111">Return Value</span></span>  
  
|<span data-ttu-id="bd480-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd480-112">HRESULT</span></span>|<span data-ttu-id="bd480-113">说明</span><span class="sxs-lookup"><span data-stu-id="bd480-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bd480-114">`EnumAssemblyRefs` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="bd480-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bd480-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="bd480-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="bd480-116">在这种情况下，`pcTokens` 设置为零。</span><span class="sxs-lookup"><span data-stu-id="bd480-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd480-117">要求</span><span class="sxs-lookup"><span data-stu-id="bd480-117">Requirements</span></span>  
 <span data-ttu-id="bd480-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd480-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd480-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="bd480-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd480-120">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bd480-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd480-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd480-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd480-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd480-122">See also</span></span>

- [<span data-ttu-id="bd480-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="bd480-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
