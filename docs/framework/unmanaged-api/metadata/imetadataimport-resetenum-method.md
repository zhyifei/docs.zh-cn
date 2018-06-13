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
ms.openlocfilehash: 56fc0273fb2c1b77c74d7a1d853886f47170497e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447923"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="3661b-102">IMetaDataImport::ResetEnum 方法</span><span class="sxs-lookup"><span data-stu-id="3661b-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="3661b-103">将指定的枚举器重置到指定位置。</span><span class="sxs-lookup"><span data-stu-id="3661b-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3661b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3661b-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3661b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3661b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="3661b-106">[in]枚举数重置。</span><span class="sxs-lookup"><span data-stu-id="3661b-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="3661b-107">[in]将枚举器新位置。</span><span class="sxs-lookup"><span data-stu-id="3661b-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3661b-108">要求</span><span class="sxs-lookup"><span data-stu-id="3661b-108">Requirements</span></span>  
 <span data-ttu-id="3661b-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3661b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3661b-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3661b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3661b-111">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3661b-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3661b-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3661b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3661b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3661b-113">See Also</span></span>  
 [<span data-ttu-id="3661b-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3661b-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3661b-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3661b-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
