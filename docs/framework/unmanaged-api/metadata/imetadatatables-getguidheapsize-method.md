---
title: "IMetaDataTables::GetGuidHeapSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetGuidHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 297b8f3572f67aa5e8b17b1b94d71f59962cfe68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="150c9-102">IMetaDataTables::GetGuidHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="150c9-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="150c9-103">获取用字节表示，GUID 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="150c9-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="150c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="150c9-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="150c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="150c9-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="150c9-106">[out]指向以字节为单位，GUID 堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="150c9-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="150c9-107">惠?</span><span class="sxs-lookup"><span data-stu-id="150c9-107">Requirements</span></span>  
 <span data-ttu-id="150c9-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="150c9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="150c9-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="150c9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="150c9-110">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="150c9-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="150c9-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="150c9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150c9-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="150c9-112">See Also</span></span>  
 [<span data-ttu-id="150c9-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="150c9-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="150c9-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="150c9-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
