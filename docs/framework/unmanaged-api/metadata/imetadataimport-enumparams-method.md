---
title: "IMetaDataImport::EnumParams 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42555e1300016222e9ea8064e90fa3062d79db6a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="c2969-102">IMetaDataImport::EnumParams 方法</span><span class="sxs-lookup"><span data-stu-id="c2969-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="c2969-103">枚举 ParamDef 标记，这些标记表示指定的 MethodDef 标记所引用的方法的参数。</span><span class="sxs-lookup"><span data-stu-id="c2969-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2969-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2969-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2969-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2969-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c2969-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="c2969-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c2969-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c2969-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="c2969-108">[in]表示具有要枚举的参数的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="c2969-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="c2969-109">[out]用于存储的 ParamDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="c2969-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c2969-110">[in] `rParams` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c2969-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c2969-111">[out]在中返回的 ParamDef 标记数`rParams`。</span><span class="sxs-lookup"><span data-stu-id="c2969-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2969-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c2969-112">Return Value</span></span>  
  
|<span data-ttu-id="c2969-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2969-113">HRESULT</span></span>|<span data-ttu-id="c2969-114">描述</span><span class="sxs-lookup"><span data-stu-id="c2969-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c2969-115">`EnumParams`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c2969-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c2969-116">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="c2969-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="c2969-117">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="c2969-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2969-118">要求</span><span class="sxs-lookup"><span data-stu-id="c2969-118">Requirements</span></span>  
 <span data-ttu-id="c2969-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2969-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2969-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2969-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2969-121">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c2969-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2969-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2969-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2969-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2969-123">See Also</span></span>  
 [<span data-ttu-id="c2969-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c2969-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c2969-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c2969-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
