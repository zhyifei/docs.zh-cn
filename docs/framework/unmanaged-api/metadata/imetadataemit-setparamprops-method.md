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
ms.openlocfilehash: ac76a9af6839ea08169c8b9c143fa96066e954ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="e9907-102">IMetaDataEmit::SetParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="e9907-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="e9907-103">设置或更改功能的已定义的调用的方法参数[imetadataemit:: Defineparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e9907-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9907-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9907-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e9907-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9907-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="e9907-106">[in]目标参数的标记。</span><span class="sxs-lookup"><span data-stu-id="e9907-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="e9907-107">[in]以 Unicode 参数的名称。</span><span class="sxs-lookup"><span data-stu-id="e9907-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="e9907-108">[in]参数的标志。</span><span class="sxs-lookup"><span data-stu-id="e9907-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="e9907-109">[in]ELEMENT_TYPE_ * 的常量值。</span><span class="sxs-lookup"><span data-stu-id="e9907-109">[in] The ELEMENT_TYPE_* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e9907-110">[in]参数的常量值。</span><span class="sxs-lookup"><span data-stu-id="e9907-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="e9907-111">[in]以 (Unicode) 字符为单位的大小`pValue`。</span><span class="sxs-lookup"><span data-stu-id="e9907-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9907-112">要求</span><span class="sxs-lookup"><span data-stu-id="e9907-112">Requirements</span></span>  
 <span data-ttu-id="e9907-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9907-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9907-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9907-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9907-115">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e9907-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9907-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9907-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9907-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9907-117">See Also</span></span>  
 [<span data-ttu-id="e9907-118">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="e9907-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e9907-119">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="e9907-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
