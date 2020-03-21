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
ms.openlocfilehash: 6a4489d094974eb872b39824ceb185b0cbe48625
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177828"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="936d1-102">IMetaDataAssemblyImport::EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="936d1-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="936d1-103">枚举程序集`mdAssemblyRef`清单中定义的实例。</span><span class="sxs-lookup"><span data-stu-id="936d1-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="936d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="936d1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="936d1-105">parameters</span><span class="sxs-lookup"><span data-stu-id="936d1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="936d1-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="936d1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="936d1-107">当首次调用该方法时，`EnumAssemblyRefs`这必须是 null 值。</span><span class="sxs-lookup"><span data-stu-id="936d1-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="936d1-108">[出]元数据令牌的`mdAssemblyRef`枚举。</span><span class="sxs-lookup"><span data-stu-id="936d1-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="936d1-109">[在]可放置在`rAssemblyRefs`数组中的最大令牌数。</span><span class="sxs-lookup"><span data-stu-id="936d1-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="936d1-110">[出]实际放置在 中的`rAssemblyRefs`令牌数。</span><span class="sxs-lookup"><span data-stu-id="936d1-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="936d1-111">返回值</span><span class="sxs-lookup"><span data-stu-id="936d1-111">Return Value</span></span>  
  
|<span data-ttu-id="936d1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="936d1-112">HRESULT</span></span>|<span data-ttu-id="936d1-113">说明</span><span class="sxs-lookup"><span data-stu-id="936d1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="936d1-114">`EnumAssemblyRefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="936d1-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="936d1-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="936d1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="936d1-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="936d1-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="936d1-117">要求</span><span class="sxs-lookup"><span data-stu-id="936d1-117">Requirements</span></span>  
 <span data-ttu-id="936d1-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="936d1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="936d1-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="936d1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="936d1-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="936d1-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="936d1-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="936d1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936d1-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="936d1-122">See also</span></span>

- [<span data-ttu-id="936d1-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="936d1-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
