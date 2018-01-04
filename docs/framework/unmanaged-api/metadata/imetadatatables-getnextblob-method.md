---
title: "IMetaDataTables::GetNextBlob 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399cf6626e7a56584829b2a8417958ce7e608727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="0a883-102">IMetaDataTables::GetNextBlob 方法</span><span class="sxs-lookup"><span data-stu-id="0a883-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="0a883-103">获取表中的下一步二进制大型对象 (BLOB) 的索引。</span><span class="sxs-lookup"><span data-stu-id="0a883-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a883-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a883-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a883-105">参数</span><span class="sxs-lookup"><span data-stu-id="0a883-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="0a883-106">[in]返回的 Blob 列的索引。</span><span class="sxs-lookup"><span data-stu-id="0a883-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="0a883-107">[out]指向下一个 BLOB 的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="0a883-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a883-108">惠?</span><span class="sxs-lookup"><span data-stu-id="0a883-108">Requirements</span></span>  
 <span data-ttu-id="0a883-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a883-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a883-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a883-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a883-111">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0a883-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a883-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a883-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a883-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a883-113">See Also</span></span>  
 [<span data-ttu-id="0a883-114">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="0a883-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="0a883-115">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="0a883-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
