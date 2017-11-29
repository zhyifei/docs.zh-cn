---
title: "IMetaDataTables::GetRow 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetRow
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 281824ace7696ab0fc6b3a96e0cdf307a9419313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="c1413-102">IMetaDataTables::GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="c1413-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="c1413-103">获取指定的行索引处，在指定的表索引的表中的一行。</span><span class="sxs-lookup"><span data-stu-id="c1413-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1413-104">语法</span><span class="sxs-lookup"><span data-stu-id="c1413-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1413-105">参数</span><span class="sxs-lookup"><span data-stu-id="c1413-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="c1413-106">[in]将从中检索行的表的索引。</span><span class="sxs-lookup"><span data-stu-id="c1413-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="c1413-107">[in]要获取的行索引。</span><span class="sxs-lookup"><span data-stu-id="c1413-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="c1413-108">[out]指向行的指针。</span><span class="sxs-lookup"><span data-stu-id="c1413-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1413-109">备注</span><span class="sxs-lookup"><span data-stu-id="c1413-109">Remarks</span></span>  
 <span data-ttu-id="c1413-110">不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="c1413-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="c1413-111">GUID 表有关的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"第 ii 部分： 元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="c1413-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="c1413-112">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](http://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="c1413-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1413-113">要求</span><span class="sxs-lookup"><span data-stu-id="c1413-113">Requirements</span></span>  
 <span data-ttu-id="c1413-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1413-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1413-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1413-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1413-116">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c1413-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1413-117">**.NET framework 版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1413-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1413-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1413-118">See Also</span></span>  
 [<span data-ttu-id="c1413-119">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="c1413-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="c1413-120">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="c1413-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
