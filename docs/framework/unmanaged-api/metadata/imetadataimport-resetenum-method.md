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
ms.openlocfilehash: 3f965ab215ff861c6df61de82dcbbea6b389c8da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426776"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="353fc-102">IMetaDataImport::ResetEnum 方法</span><span class="sxs-lookup"><span data-stu-id="353fc-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="353fc-103">将指定的枚举器重置到指定位置。</span><span class="sxs-lookup"><span data-stu-id="353fc-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="353fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="353fc-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="353fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="353fc-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="353fc-106">中要重置的枚举数。</span><span class="sxs-lookup"><span data-stu-id="353fc-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="353fc-107">中要放置枚举器的新位置。</span><span class="sxs-lookup"><span data-stu-id="353fc-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="353fc-108">要求</span><span class="sxs-lookup"><span data-stu-id="353fc-108">Requirements</span></span>  
 <span data-ttu-id="353fc-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="353fc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="353fc-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="353fc-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="353fc-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="353fc-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="353fc-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="353fc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353fc-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="353fc-113">See also</span></span>

- [<span data-ttu-id="353fc-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="353fc-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="353fc-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="353fc-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
