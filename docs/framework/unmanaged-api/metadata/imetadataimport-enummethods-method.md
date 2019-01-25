---
title: IMetaDataImport::EnumMethods 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 668c7298a9543cce93cce324672334c9ec1e8cd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732812"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="2d82b-102">IMetaDataImport::EnumMethods 方法</span><span class="sxs-lookup"><span data-stu-id="2d82b-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="2d82b-103">枚举表示指定类型的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="2d82b-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d82b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d82b-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d82b-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d82b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2d82b-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="2d82b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2d82b-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2d82b-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="2d82b-108">[in]方法来枚举与表示类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="2d82b-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="2d82b-109">[out]要存储的 MethodDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="2d82b-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2d82b-110">[in]最大大小的 MethodDef`rMethods`数组。</span><span class="sxs-lookup"><span data-stu-id="2d82b-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2d82b-111">[out]在中返回的 MethodDef 标记数`rMethods`。</span><span class="sxs-lookup"><span data-stu-id="2d82b-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d82b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2d82b-112">Return Value</span></span>  
  
|<span data-ttu-id="2d82b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d82b-113">HRESULT</span></span>|<span data-ttu-id="2d82b-114">描述</span><span class="sxs-lookup"><span data-stu-id="2d82b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2d82b-115">`EnumMethods` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2d82b-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2d82b-116">没有要枚举的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="2d82b-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="2d82b-117">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="2d82b-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d82b-118">要求</span><span class="sxs-lookup"><span data-stu-id="2d82b-118">Requirements</span></span>  
 <span data-ttu-id="2d82b-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d82b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d82b-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2d82b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d82b-121">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2d82b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2d82b-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d82b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d82b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d82b-123">See also</span></span>
- [<span data-ttu-id="2d82b-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="2d82b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2d82b-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="2d82b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
