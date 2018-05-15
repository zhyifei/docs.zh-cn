---
title: IMetaDataEmit2::SetGenericParamProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d74ee7512f640ab906f1119f61e4998b5e882eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="4e545-102">IMetaDataEmit2::SetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="4e545-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="4e545-103">设置指定标记所引用的泛型参数定义的属性值。</span><span class="sxs-lookup"><span data-stu-id="4e545-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e545-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e545-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e545-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e545-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="4e545-106">[in]若要设置值的泛型参数定义标记。</span><span class="sxs-lookup"><span data-stu-id="4e545-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="4e545-107">[in]值为[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)描述为泛型参数的类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="4e545-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e545-108">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="4e545-108">[in] Optional.</span></span> <span data-ttu-id="4e545-109">为其设置值参数的名称。</span><span class="sxs-lookup"><span data-stu-id="4e545-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="4e545-110">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="4e545-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="4e545-111">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="4e545-111">[in] Optional.</span></span> <span data-ttu-id="4e545-112">零终止的数组的类型约束。</span><span class="sxs-lookup"><span data-stu-id="4e545-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="4e545-113">数组成员都必须是`mdTypeDef`， `mdTypeRef`，或`mdTypeSpec`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4e545-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e545-114">要求</span><span class="sxs-lookup"><span data-stu-id="4e545-114">Requirements</span></span>  
 <span data-ttu-id="4e545-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e545-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e545-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4e545-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e545-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4e545-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e545-118">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e545-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e545-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e545-119">See Also</span></span>  
 [<span data-ttu-id="4e545-120">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="4e545-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="4e545-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="4e545-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
