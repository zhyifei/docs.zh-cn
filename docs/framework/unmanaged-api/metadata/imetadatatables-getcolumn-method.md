---
title: "IMetaDataTables::GetColumn 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 162162b972ab0e1f3de55d56c18372f2475c9846
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="c2cd8-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="c2cd8-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="c2cd8-103">获取一个指向包含的指定的列和行中给定的表的单元格的值。</span><span class="sxs-lookup"><span data-stu-id="c2cd8-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2cd8-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2cd8-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2cd8-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2cd8-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="c2cd8-106">[in]表的索引。</span><span class="sxs-lookup"><span data-stu-id="c2cd8-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="c2cd8-107">[in]表中列的索引。</span><span class="sxs-lookup"><span data-stu-id="c2cd8-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="c2cd8-108">[in]表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="c2cd8-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="c2cd8-109">[out]指向单元格中的值的指针。</span><span class="sxs-lookup"><span data-stu-id="c2cd8-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2cd8-110">惠?</span><span class="sxs-lookup"><span data-stu-id="c2cd8-110">Requirements</span></span>  
 <span data-ttu-id="c2cd8-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2cd8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2cd8-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2cd8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2cd8-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c2cd8-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2cd8-114">**.NET framework 版本**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2cd8-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cd8-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2cd8-115">See Also</span></span>  
 [<span data-ttu-id="c2cd8-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="c2cd8-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="c2cd8-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="c2cd8-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
