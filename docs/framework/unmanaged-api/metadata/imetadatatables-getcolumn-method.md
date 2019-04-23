---
title: IMetaDataTables::GetColumn 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ce56b3959c4768ef9cb6a9c551d53c5300a39e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208353"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="58d9e-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="58d9e-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="58d9e-103">获取一个指针指向包含指定的列和给定表中的行的单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="58d9e-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d9e-104">语法</span><span class="sxs-lookup"><span data-stu-id="58d9e-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d9e-105">参数</span><span class="sxs-lookup"><span data-stu-id="58d9e-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="58d9e-106">[in]表的索引。</span><span class="sxs-lookup"><span data-stu-id="58d9e-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="58d9e-107">[in]表中的列的索引。</span><span class="sxs-lookup"><span data-stu-id="58d9e-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="58d9e-108">[in]表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="58d9e-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="58d9e-109">[out]指向单元格中的值的指针。</span><span class="sxs-lookup"><span data-stu-id="58d9e-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d9e-110">要求</span><span class="sxs-lookup"><span data-stu-id="58d9e-110">Requirements</span></span>  
 <span data-ttu-id="58d9e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58d9e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d9e-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="58d9e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58d9e-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58d9e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58d9e-114">**.NET framework 版本** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d9e-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d9e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="58d9e-115">See also</span></span>

- [<span data-ttu-id="58d9e-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="58d9e-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="58d9e-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="58d9e-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
