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
ms.openlocfilehash: 4c998d70fa5dd41ab4c1656f129bb77767a8ab97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574616"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="4af04-102">IMetaDataEmit2::SetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="4af04-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="4af04-103">设置指定标记所引用的泛型参数定义的属性值。</span><span class="sxs-lookup"><span data-stu-id="4af04-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af04-104">语法</span><span class="sxs-lookup"><span data-stu-id="4af04-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4af04-105">参数</span><span class="sxs-lookup"><span data-stu-id="4af04-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="4af04-106">[in]有关泛型参数定义的信息为其设置值标记。</span><span class="sxs-lookup"><span data-stu-id="4af04-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="4af04-107">[in]值为[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)描述泛型参数的类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="4af04-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="4af04-108">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="4af04-108">[in] Optional.</span></span> <span data-ttu-id="4af04-109">要为其设置值的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="4af04-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="4af04-110">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="4af04-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="4af04-111">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="4af04-111">[in] Optional.</span></span> <span data-ttu-id="4af04-112">类型约束的以零终止的数组。</span><span class="sxs-lookup"><span data-stu-id="4af04-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="4af04-113">数组成员都必须是`mdTypeDef`， `mdTypeRef`，或`mdTypeSpec`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4af04-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af04-114">要求</span><span class="sxs-lookup"><span data-stu-id="4af04-114">Requirements</span></span>  
 <span data-ttu-id="4af04-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4af04-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af04-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4af04-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4af04-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4af04-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4af04-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af04-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af04-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4af04-119">See also</span></span>
- [<span data-ttu-id="4af04-120">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="4af04-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="4af04-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="4af04-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
