---
title: "IMetaDataTables::GetUserStringHeapSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetUserStringHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 69c78afddc50930d4390b516cece819f124a7933
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="795d3-102">IMetaDataTables::GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="795d3-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="795d3-103">获取用字节表示，用户字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="795d3-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="795d3-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="795d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="795d3-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="795d3-106">[out]指向以字节为单位的用户字符串堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="795d3-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="795d3-107">要求</span><span class="sxs-lookup"><span data-stu-id="795d3-107">Requirements</span></span>  
 <span data-ttu-id="795d3-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="795d3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="795d3-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="795d3-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="795d3-110">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="795d3-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="795d3-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="795d3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795d3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="795d3-112">See Also</span></span>  
 [<span data-ttu-id="795d3-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="795d3-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="795d3-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="795d3-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
