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
ms.openlocfilehash: 9c380d363830eb6b4c47110d50cdb4d08e4568d8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499805"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="bdd5f-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="bdd5f-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="bdd5f-103">获取一个指针指向包含指定的列和给定表中的行的单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="bdd5f-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdd5f-104">语法</span><span class="sxs-lookup"><span data-stu-id="bdd5f-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdd5f-105">参数</span><span class="sxs-lookup"><span data-stu-id="bdd5f-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="bdd5f-106">[in]表的索引。</span><span class="sxs-lookup"><span data-stu-id="bdd5f-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="bdd5f-107">[in]表中的列的索引。</span><span class="sxs-lookup"><span data-stu-id="bdd5f-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="bdd5f-108">[in]表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="bdd5f-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="bdd5f-109">[out]指向单元格中的值的指针。</span><span class="sxs-lookup"><span data-stu-id="bdd5f-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdd5f-110">要求</span><span class="sxs-lookup"><span data-stu-id="bdd5f-110">Requirements</span></span>  
 <span data-ttu-id="bdd5f-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd5f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdd5f-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bdd5f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdd5f-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bdd5f-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bdd5f-114">**.NET framework 版本** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdd5f-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd5f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdd5f-115">See also</span></span>
- [<span data-ttu-id="bdd5f-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="bdd5f-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="bdd5f-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="bdd5f-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
