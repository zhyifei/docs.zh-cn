---
title: IMetaDataImport::EnumMethodImpls 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebfd41a232a3284f79e4229a8845bf5a34f9d1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574763"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="09771-102">IMetaDataImport::EnumMethodImpls 方法</span><span class="sxs-lookup"><span data-stu-id="09771-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="09771-103">枚举表示指定类型的方法的 MethodBody 和 MethodDeclaration 标记。</span><span class="sxs-lookup"><span data-stu-id="09771-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09771-104">语法</span><span class="sxs-lookup"><span data-stu-id="09771-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdToken     rMethodBody[],   
   [out]     mdToken     rMethodDecl[],   
   [in]      ULONG       cMax,   
   [in]      ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09771-105">参数</span><span class="sxs-lookup"><span data-stu-id="09771-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="09771-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="09771-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="09771-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="09771-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="09771-108">[in]TypeDef 的类型的令牌要枚举的方法实现。</span><span class="sxs-lookup"><span data-stu-id="09771-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="09771-109">[out]要存储 MethodBody 令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="09771-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="09771-110">[out]要存储 MethodDeclaration 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="09771-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="09771-111">[in]最大大小`rMethodBody`和`rMethodDecl`数组。</span><span class="sxs-lookup"><span data-stu-id="09771-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="09771-112">[in]方法中返回的实际数量`rMethodBody`和`rMethodDecl`。</span><span class="sxs-lookup"><span data-stu-id="09771-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09771-113">返回值</span><span class="sxs-lookup"><span data-stu-id="09771-113">Return Value</span></span>  
  
|<span data-ttu-id="09771-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09771-114">HRESULT</span></span>|<span data-ttu-id="09771-115">描述</span><span class="sxs-lookup"><span data-stu-id="09771-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="09771-116">`EnumMethodImpls` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="09771-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="09771-117">没有要枚举的方法标记。</span><span class="sxs-lookup"><span data-stu-id="09771-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="09771-118">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="09771-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09771-119">要求</span><span class="sxs-lookup"><span data-stu-id="09771-119">Requirements</span></span>  
 <span data-ttu-id="09771-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09771-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09771-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="09771-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09771-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="09771-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09771-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09771-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09771-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="09771-124">See also</span></span>
- [<span data-ttu-id="09771-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="09771-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="09771-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="09771-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
