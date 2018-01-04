---
title: "IMetaDataEmit::SetParamProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8ada9deddf8528321797c1f9bd06b5b775ac4bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="0ff0a-102">IMetaDataEmit::SetParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="0ff0a-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="0ff0a-103">设置或更改功能的已定义的调用的方法参数[imetadataemit:: Defineparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ff0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ff0a-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ff0a-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ff0a-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="0ff0a-106">[in]目标参数的标记。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="0ff0a-107">[in]以 Unicode 参数的名称。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="0ff0a-108">[in]参数的标志。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="0ff0a-109">[in]ELEMENT_TYPE_ * 的常量值。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-109">[in] The ELEMENT_TYPE_* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="0ff0a-110">[in]参数的常量值。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="0ff0a-111">[in]以 (Unicode) 字符为单位的大小`pValue`。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ff0a-112">惠?</span><span class="sxs-lookup"><span data-stu-id="0ff0a-112">Requirements</span></span>  
 <span data-ttu-id="0ff0a-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ff0a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ff0a-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ff0a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ff0a-115">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0ff0a-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ff0a-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ff0a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff0a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ff0a-117">See Also</span></span>  
 [<span data-ttu-id="0ff0a-118">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="0ff0a-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0ff0a-119">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="0ff0a-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
