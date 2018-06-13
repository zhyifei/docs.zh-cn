---
title: IMetaDataImport::EnumMethodsWithName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cea47f8300c57362abae0c10223559319ecb2469
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448838"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="64f76-102">IMetaDataImport::EnumMethodsWithName 方法</span><span class="sxs-lookup"><span data-stu-id="64f76-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="64f76-103">枚举具有指定名称并且由指定的 TypeDef 标记所引用的类型定义的方法。</span><span class="sxs-lookup"><span data-stu-id="64f76-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f76-104">语法</span><span class="sxs-lookup"><span data-stu-id="64f76-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64f76-105">参数</span><span class="sxs-lookup"><span data-stu-id="64f76-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="64f76-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="64f76-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="64f76-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="64f76-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="64f76-108">[in]表示其方法来枚举的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="64f76-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="64f76-109">[in]限制在枚举的作用域的名称。</span><span class="sxs-lookup"><span data-stu-id="64f76-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="64f76-110">[out]用于存储的 MethodDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="64f76-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="64f76-111">[in] `rMethods` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="64f76-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="64f76-112">[out]在中返回的 MethodDef 标记数`rMethods`。</span><span class="sxs-lookup"><span data-stu-id="64f76-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64f76-113">备注</span><span class="sxs-lookup"><span data-stu-id="64f76-113">Remarks</span></span>  
 <span data-ttu-id="64f76-114">此方法枚举字段和方法，但不是属性或事件。</span><span class="sxs-lookup"><span data-stu-id="64f76-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="64f76-115">与不同[imetadataimport:: Enummethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)，`EnumMethodsWithName`放弃不具有指定的名称的所有方法令牌。</span><span class="sxs-lookup"><span data-stu-id="64f76-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64f76-116">返回值</span><span class="sxs-lookup"><span data-stu-id="64f76-116">Return Value</span></span>  
  
|<span data-ttu-id="64f76-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64f76-117">HRESULT</span></span>|<span data-ttu-id="64f76-118">描述</span><span class="sxs-lookup"><span data-stu-id="64f76-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="64f76-119">`EnumMethodsWithName` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="64f76-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="64f76-120">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="64f76-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="64f76-121">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="64f76-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64f76-122">要求</span><span class="sxs-lookup"><span data-stu-id="64f76-122">Requirements</span></span>  
 <span data-ttu-id="64f76-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64f76-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64f76-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64f76-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64f76-125">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="64f76-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64f76-126">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64f76-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f76-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="64f76-127">See Also</span></span>  
 [<span data-ttu-id="64f76-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="64f76-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="64f76-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="64f76-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
