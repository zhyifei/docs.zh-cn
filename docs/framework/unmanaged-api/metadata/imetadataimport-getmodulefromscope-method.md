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
ms.openlocfilehash: 931b17858465d4ff380069fc2cf2bb37cb7a7ffc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718177"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="d4e86-102">IMetaDataImport::GetModuleFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="d4e86-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="d4e86-103">获取在当前元数据范围内引用的模块的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="d4e86-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e86-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4e86-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4e86-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4e86-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="d4e86-106">[out]指向表示当前元数据范围内引用的模块的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="d4e86-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4e86-107">要求</span><span class="sxs-lookup"><span data-stu-id="d4e86-107">Requirements</span></span>  
 <span data-ttu-id="d4e86-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4e86-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4e86-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d4e86-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4e86-110">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d4e86-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4e86-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4e86-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e86-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4e86-112">See also</span></span>
- [<span data-ttu-id="d4e86-113">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d4e86-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d4e86-114">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d4e86-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
