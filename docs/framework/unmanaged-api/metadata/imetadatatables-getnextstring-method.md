---
title: "IMetaDataTables::GetNextString 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2bf16f6debd50729a95a4e887a01c1158b7a937
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="e0031-102">IMetaDataTables::GetNextString 方法</span><span class="sxs-lookup"><span data-stu-id="e0031-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="e0031-103">获取当前的表列中的下一步的字符串的索引。</span><span class="sxs-lookup"><span data-stu-id="e0031-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0031-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0031-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0031-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0031-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="e0031-106">[in]字符串表列中的索引值。</span><span class="sxs-lookup"><span data-stu-id="e0031-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="e0031-107">[out]指向列中的下一步字符串的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="e0031-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0031-108">惠?</span><span class="sxs-lookup"><span data-stu-id="e0031-108">Requirements</span></span>  
 <span data-ttu-id="e0031-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0031-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0031-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e0031-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0031-111">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e0031-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0031-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0031-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0031-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0031-113">See Also</span></span>  
 [<span data-ttu-id="e0031-114">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="e0031-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="e0031-115">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="e0031-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
