---
title: "IMetaDataImport::GetModuleFromScope 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleFromScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d7a9987f9a557cda79483e46c1798d471aa13944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="13d8e-102">IMetaDataImport::GetModuleFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="13d8e-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="13d8e-103">获取当前元数据范围内引用的模块元数据标记。</span><span class="sxs-lookup"><span data-stu-id="13d8e-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="13d8e-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13d8e-105">参数</span><span class="sxs-lookup"><span data-stu-id="13d8e-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="13d8e-106">[out]指向表示当前元数据范围内引用的模块的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="13d8e-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d8e-107">要求</span><span class="sxs-lookup"><span data-stu-id="13d8e-107">Requirements</span></span>  
 <span data-ttu-id="13d8e-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13d8e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13d8e-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13d8e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13d8e-110">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13d8e-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13d8e-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13d8e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d8e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13d8e-112">See Also</span></span>  
 [<span data-ttu-id="13d8e-113">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="13d8e-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="13d8e-114">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="13d8e-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
