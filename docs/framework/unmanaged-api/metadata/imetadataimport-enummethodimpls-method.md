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
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175468"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="6e033-102">IMetaDataImport::EnumMethodImpls 方法</span><span class="sxs-lookup"><span data-stu-id="6e033-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="6e033-103">枚举表示指定类型的方法的 MethodBody 和 MethodDeclaration 标记。</span><span class="sxs-lookup"><span data-stu-id="6e033-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e033-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e033-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e033-105">parameters</span><span class="sxs-lookup"><span data-stu-id="6e033-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6e033-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="6e033-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6e033-107">对于此方法的第一次调用，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6e033-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="6e033-108">[在]方法要枚举的类型的类型的 TypeDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="6e033-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="6e033-109">[出]要存储方法体令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="6e033-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="6e033-110">[出]要存储方法声明令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="6e033-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6e033-111">[在]`rMethodBody`和`rMethodDecl`数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="6e033-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6e033-112">[在]在 和`rMethodBody``rMethodDecl`中返回的实际方法数。</span><span class="sxs-lookup"><span data-stu-id="6e033-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e033-113">返回值</span><span class="sxs-lookup"><span data-stu-id="6e033-113">Return Value</span></span>  
  
|<span data-ttu-id="6e033-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e033-114">HRESULT</span></span>|<span data-ttu-id="6e033-115">说明</span><span class="sxs-lookup"><span data-stu-id="6e033-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6e033-116">`EnumMethodImpls`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6e033-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6e033-117">没有要枚举的方法令牌。</span><span class="sxs-lookup"><span data-stu-id="6e033-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="6e033-118">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="6e033-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e033-119">要求</span><span class="sxs-lookup"><span data-stu-id="6e033-119">Requirements</span></span>  
 <span data-ttu-id="6e033-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e033-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e033-121">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="6e033-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e033-122">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="6e033-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e033-123">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e033-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e033-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e033-124">See also</span></span>

- [<span data-ttu-id="6e033-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6e033-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6e033-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="6e033-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
