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
ms.openlocfilehash: 3dd82588cf2dbf92fdda66fd7674c17ddc8b7306
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177187"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="f5c37-102">IMetaDataImport::ResetEnum 方法</span><span class="sxs-lookup"><span data-stu-id="f5c37-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="f5c37-103">将指定的枚举器重置到指定位置。</span><span class="sxs-lookup"><span data-stu-id="f5c37-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c37-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5c37-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5c37-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f5c37-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="f5c37-106">[在]要重置的枚举器。</span><span class="sxs-lookup"><span data-stu-id="f5c37-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="f5c37-107">[在]放置枚举器的新位置。</span><span class="sxs-lookup"><span data-stu-id="f5c37-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5c37-108">要求</span><span class="sxs-lookup"><span data-stu-id="f5c37-108">Requirements</span></span>  
 <span data-ttu-id="f5c37-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5c37-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5c37-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="f5c37-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5c37-111">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="f5c37-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5c37-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5c37-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c37-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5c37-113">See also</span></span>

- [<span data-ttu-id="f5c37-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f5c37-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f5c37-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f5c37-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
