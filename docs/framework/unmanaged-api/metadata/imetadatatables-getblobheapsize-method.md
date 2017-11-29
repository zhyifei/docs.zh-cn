---
title: "IMetaDataTables::GetBlobHeapSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetBlobHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 796a7246a90f60627906b1febb6fbe15152ed8e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="9efa8-102">IMetaDataTables::GetBlobHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="9efa8-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="9efa8-103">获取用字节表示，二进制大型对象 (BLOB) 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="9efa8-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efa8-104">语法</span><span class="sxs-lookup"><span data-stu-id="9efa8-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="9efa8-105">参数</span><span class="sxs-lookup"><span data-stu-id="9efa8-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="9efa8-106">[out]指向以字节为单位的 BLOB 堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="9efa8-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efa8-107">要求</span><span class="sxs-lookup"><span data-stu-id="9efa8-107">Requirements</span></span>  
 <span data-ttu-id="9efa8-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9efa8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efa8-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9efa8-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9efa8-110">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9efa8-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9efa8-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efa8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efa8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9efa8-112">See Also</span></span>  
 [<span data-ttu-id="9efa8-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="9efa8-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="9efa8-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="9efa8-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
