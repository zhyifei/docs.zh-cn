---
title: IMetaDataImport::ResetEnum 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5543313a8d7a5589e115d609923aa0e75d3e275
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484961"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="c099d-102">IMetaDataImport::ResetEnum 方法</span><span class="sxs-lookup"><span data-stu-id="c099d-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="c099d-103">将指定的枚举器重置到指定位置。</span><span class="sxs-lookup"><span data-stu-id="c099d-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c099d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c099d-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c099d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c099d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c099d-106">[in]若要重置枚举器。</span><span class="sxs-lookup"><span data-stu-id="c099d-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="c099d-107">[in]在其中放置枚举器的新位置。</span><span class="sxs-lookup"><span data-stu-id="c099d-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c099d-108">要求</span><span class="sxs-lookup"><span data-stu-id="c099d-108">Requirements</span></span>  
 <span data-ttu-id="c099d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c099d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c099d-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c099d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c099d-111">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c099d-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c099d-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c099d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c099d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c099d-113">See also</span></span>
- [<span data-ttu-id="c099d-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c099d-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c099d-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c099d-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
