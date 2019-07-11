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
ms.openlocfilehash: 22f9ceab2f01ac12762710f313c56f3f0ee4e6be
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781536"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="ba470-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="ba470-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="ba470-103">获取一个指针指向包含指定的列和给定表中的行的单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="ba470-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba470-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba470-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba470-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba470-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="ba470-106">[in]表的索引。</span><span class="sxs-lookup"><span data-stu-id="ba470-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="ba470-107">[in]表中的列的索引。</span><span class="sxs-lookup"><span data-stu-id="ba470-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="ba470-108">[in]表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="ba470-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="ba470-109">[out]指向单元格中的值的指针。</span><span class="sxs-lookup"><span data-stu-id="ba470-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba470-110">要求</span><span class="sxs-lookup"><span data-stu-id="ba470-110">Requirements</span></span>  
 <span data-ttu-id="ba470-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba470-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba470-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba470-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba470-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ba470-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba470-114">**.NET framework 版本** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba470-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba470-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba470-115">See also</span></span>

- [<span data-ttu-id="ba470-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="ba470-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ba470-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="ba470-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
