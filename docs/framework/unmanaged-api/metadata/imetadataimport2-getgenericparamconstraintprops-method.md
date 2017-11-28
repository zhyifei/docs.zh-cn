---
title: "IMetaDataImport2::GetGenericParamConstraintProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamConstraintProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7d1e560dd511758652e1acbc262b4ddc3efdd12c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="6d84e-102">IMetaDataImport2::GetGenericParamConstraintProps 方法</span><span class="sxs-lookup"><span data-stu-id="6d84e-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="6d84e-103">获取具有指定的约束标记所表示的泛型参数约束关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="6d84e-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d84e-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d84e-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d84e-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d84e-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="6d84e-106">[in]为泛型参数约束为其返回元数据标记。</span><span class="sxs-lookup"><span data-stu-id="6d84e-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="6d84e-107">[out]指向表示的约束的泛型参数的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="6d84e-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="6d84e-108">[out]指向表示的约束 TypeDef、 TypeRef 或 TypeSpec 标记的`ptGenericParam`。</span><span class="sxs-lookup"><span data-stu-id="6d84e-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d84e-109">要求</span><span class="sxs-lookup"><span data-stu-id="6d84e-109">Requirements</span></span>  
 <span data-ttu-id="6d84e-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d84e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d84e-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d84e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d84e-112">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d84e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d84e-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d84e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d84e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d84e-114">See Also</span></span>  
 [<span data-ttu-id="6d84e-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="6d84e-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="6d84e-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6d84e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
