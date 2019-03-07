---
title: IMetaDataImport::GetModuleFromScope 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1118c29acd926821e3b5db31694df9935bdefb9e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468801"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="7f383-102">IMetaDataImport::GetModuleFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="7f383-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="7f383-103">获取在当前元数据范围内引用的模块的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="7f383-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f383-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f383-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f383-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f383-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="7f383-106">[out]指向表示当前元数据范围内引用的模块的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="7f383-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f383-107">要求</span><span class="sxs-lookup"><span data-stu-id="7f383-107">Requirements</span></span>  
 <span data-ttu-id="7f383-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f383-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f383-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7f383-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f383-110">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7f383-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f383-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f383-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f383-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f383-112">See also</span></span>
- [<span data-ttu-id="7f383-113">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7f383-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7f383-114">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7f383-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
