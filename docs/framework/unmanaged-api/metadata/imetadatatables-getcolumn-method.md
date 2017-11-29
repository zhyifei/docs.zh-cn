---
title: "IMetaDataTables::GetColumn 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetColumn
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: abc6e5ad5ec1da5ac92dafb455e44d0ccfdade4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="4fac6-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="4fac6-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="4fac6-103">获取一个指向包含的指定的列和行中给定的表的单元格的值。</span><span class="sxs-lookup"><span data-stu-id="4fac6-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fac6-104">语法</span><span class="sxs-lookup"><span data-stu-id="4fac6-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4fac6-105">参数</span><span class="sxs-lookup"><span data-stu-id="4fac6-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="4fac6-106">[in]表的索引。</span><span class="sxs-lookup"><span data-stu-id="4fac6-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="4fac6-107">[in]表中列的索引。</span><span class="sxs-lookup"><span data-stu-id="4fac6-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="4fac6-108">[in]表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="4fac6-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="4fac6-109">[out]指向单元格中的值的指针。</span><span class="sxs-lookup"><span data-stu-id="4fac6-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fac6-110">要求</span><span class="sxs-lookup"><span data-stu-id="4fac6-110">Requirements</span></span>  
 <span data-ttu-id="4fac6-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4fac6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fac6-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4fac6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4fac6-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4fac6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4fac6-114">**.NET framework 版本**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fac6-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fac6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fac6-115">See Also</span></span>  
 [<span data-ttu-id="4fac6-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="4fac6-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="4fac6-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="4fac6-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
