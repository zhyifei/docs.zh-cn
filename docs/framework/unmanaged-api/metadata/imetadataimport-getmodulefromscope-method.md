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
ms.openlocfilehash: f40e6bfdbebdadc41da52564348c6070c18372c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194673"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="f4454-102">IMetaDataImport::GetModuleFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="f4454-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="f4454-103">获取在当前元数据范围内引用的模块的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="f4454-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4454-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4454-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4454-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4454-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="f4454-106">[out]指向表示当前元数据范围内引用的模块的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="f4454-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4454-107">要求</span><span class="sxs-lookup"><span data-stu-id="f4454-107">Requirements</span></span>  
 <span data-ttu-id="f4454-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4454-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4454-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f4454-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4454-110">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f4454-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f4454-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f4454-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4454-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4454-112">See also</span></span>

- [<span data-ttu-id="f4454-113">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f4454-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f4454-114">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f4454-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
