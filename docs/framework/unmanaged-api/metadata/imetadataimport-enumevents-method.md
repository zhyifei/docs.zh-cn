---
title: "IMetaDataImport::EnumEvents 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumEvents
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed783cf80fb068656855c2c06ab814f665f1cede
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="e1566-102">IMetaDataImport::EnumEvents 方法</span><span class="sxs-lookup"><span data-stu-id="e1566-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="e1566-103">枚举指定的 TypeDef 标记的事件定义标记。</span><span class="sxs-lookup"><span data-stu-id="e1566-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1566-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1566-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1566-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1566-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e1566-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="e1566-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="e1566-107">[in]要枚举其事件定义的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="e1566-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="e1566-108">[out]返回的事件的数组。</span><span class="sxs-lookup"><span data-stu-id="e1566-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e1566-109">[in] `rEvents` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="e1566-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="e1566-110">[out]在中返回的事件的实际数`rEvents`。</span><span class="sxs-lookup"><span data-stu-id="e1566-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1566-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e1566-111">Return Value</span></span>  
  
|<span data-ttu-id="e1566-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1566-112">HRESULT</span></span>|<span data-ttu-id="e1566-113">描述</span><span class="sxs-lookup"><span data-stu-id="e1566-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e1566-114">`EnumEvents`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e1566-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e1566-115">没有要枚举的事件。</span><span class="sxs-lookup"><span data-stu-id="e1566-115">There are no events to enumerate.</span></span> <span data-ttu-id="e1566-116">在这种情况下，`pcEvents`为零。</span><span class="sxs-lookup"><span data-stu-id="e1566-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1566-117">惠?</span><span class="sxs-lookup"><span data-stu-id="e1566-117">Requirements</span></span>  
 <span data-ttu-id="e1566-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1566-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1566-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e1566-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1566-120">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e1566-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1566-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1566-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1566-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1566-122">See Also</span></span>  
 [<span data-ttu-id="e1566-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="e1566-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e1566-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="e1566-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
