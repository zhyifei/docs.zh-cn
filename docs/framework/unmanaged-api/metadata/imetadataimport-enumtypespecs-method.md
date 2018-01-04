---
title: "IMetaDataImport::EnumTypeSpecs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e34a3086474918c913a366c02bbf9eadf313b43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="7dc90-102">IMetaDataImport::EnumTypeSpecs 方法</span><span class="sxs-lookup"><span data-stu-id="7dc90-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="7dc90-103">枚举当前元数据范围内定义的 TypeSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="7dc90-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc90-104">语法</span><span class="sxs-lookup"><span data-stu-id="7dc90-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7dc90-105">参数</span><span class="sxs-lookup"><span data-stu-id="7dc90-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7dc90-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="7dc90-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7dc90-107">首次调用此方法，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7dc90-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="7dc90-108">[out]用于存储 TypeSpec 标记数组。</span><span class="sxs-lookup"><span data-stu-id="7dc90-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7dc90-109">[in] `rTypeSpecs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7dc90-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="7dc90-110">[out]在中返回的 TypeSpec 标记数`rTypeSpecs`。</span><span class="sxs-lookup"><span data-stu-id="7dc90-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7dc90-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7dc90-111">Return Value</span></span>  
  
|<span data-ttu-id="7dc90-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7dc90-112">HRESULT</span></span>|<span data-ttu-id="7dc90-113">描述</span><span class="sxs-lookup"><span data-stu-id="7dc90-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7dc90-114">`EnumTypeSpecs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7dc90-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7dc90-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="7dc90-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7dc90-116">在这种情况下，`pcTypeSpecs`为零。</span><span class="sxs-lookup"><span data-stu-id="7dc90-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dc90-117">备注</span><span class="sxs-lookup"><span data-stu-id="7dc90-117">Remarks</span></span>  
 <span data-ttu-id="7dc90-118">TypeSpec 令牌由[imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7dc90-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dc90-119">惠?</span><span class="sxs-lookup"><span data-stu-id="7dc90-119">Requirements</span></span>  
 <span data-ttu-id="7dc90-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7dc90-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dc90-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7dc90-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7dc90-122">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7dc90-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7dc90-123">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dc90-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc90-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dc90-124">See Also</span></span>  
 [<span data-ttu-id="7dc90-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7dc90-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7dc90-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7dc90-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
