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
ms.openlocfilehash: fa5a446ba7bfd70330601c7cbc129800761cdb7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782617"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="db79a-102">IMetaDataImport::ResetEnum 方法</span><span class="sxs-lookup"><span data-stu-id="db79a-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="db79a-103">将指定的枚举器重置到指定位置。</span><span class="sxs-lookup"><span data-stu-id="db79a-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db79a-104">语法</span><span class="sxs-lookup"><span data-stu-id="db79a-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db79a-105">参数</span><span class="sxs-lookup"><span data-stu-id="db79a-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="db79a-106">[in]若要重置枚举器。</span><span class="sxs-lookup"><span data-stu-id="db79a-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="db79a-107">[in]在其中放置枚举器的新位置。</span><span class="sxs-lookup"><span data-stu-id="db79a-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db79a-108">要求</span><span class="sxs-lookup"><span data-stu-id="db79a-108">Requirements</span></span>  
 <span data-ttu-id="db79a-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db79a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db79a-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="db79a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db79a-111">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="db79a-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db79a-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db79a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db79a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="db79a-113">See also</span></span>

- [<span data-ttu-id="db79a-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="db79a-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="db79a-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="db79a-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
