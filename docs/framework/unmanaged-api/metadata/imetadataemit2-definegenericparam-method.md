---
title: IMetaDataEmit2::DefineGenericParam 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de8547ed0ee83bafe4612bdcd62607fc94fb3f69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163717"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="3f0ce-102">IMetaDataEmit2::DefineGenericParam 方法</span><span class="sxs-lookup"><span data-stu-id="3f0ce-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="3f0ce-103">创建泛型类型参数的定义并获取该泛型类型参数的令牌。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f0ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f0ce-104">Syntax</span></span>  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f0ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f0ce-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3f0ce-106">[in]`mdTypeDef`或`mdMethodDef`表示方法或要为其定义的泛型参数的构造函数的令牌。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="3f0ce-107">[in]泛型参数的索引。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="3f0ce-108">[in]值为[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)描述泛型参数的类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="3f0ce-109">[in]参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="3f0ce-110">[in]此参数保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="3f0ce-111">[in]类型约束的以零终止的数组。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="3f0ce-112">数组成员都必须是`mdTypeDef`， `mdTypeRef`，或`mdTypeSpec`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="3f0ce-113">[out]表示泛型参数的标记。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f0ce-114">要求</span><span class="sxs-lookup"><span data-stu-id="3f0ce-114">Requirements</span></span>  
 <span data-ttu-id="3f0ce-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f0ce-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f0ce-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f0ce-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3f0ce-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f0ce-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f0ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0ce-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0ce-119">See also</span></span>

- [<span data-ttu-id="3f0ce-120">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="3f0ce-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3f0ce-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="3f0ce-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
