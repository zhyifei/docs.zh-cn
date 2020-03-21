---
title: IMetaDataTables::GetRow 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177105"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="82780-102">IMetaDataTables::GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="82780-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="82780-103">在指定的表索引的表中获取指定行索引处的行。</span><span class="sxs-lookup"><span data-stu-id="82780-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82780-104">语法</span><span class="sxs-lookup"><span data-stu-id="82780-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82780-105">parameters</span><span class="sxs-lookup"><span data-stu-id="82780-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="82780-106">[在]将从中检索行的表的索引。</span><span class="sxs-lookup"><span data-stu-id="82780-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="82780-107">[在]要获取的行的索引。</span><span class="sxs-lookup"><span data-stu-id="82780-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="82780-108">[出]指向行的指针。</span><span class="sxs-lookup"><span data-stu-id="82780-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82780-109">备注</span><span class="sxs-lookup"><span data-stu-id="82780-109">Remarks</span></span>  

  <span data-ttu-id="82780-110">我们不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="82780-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="82780-111">有关 GUID 表的信息，请参阅通用语言基础结构 （CLI） 文档，尤其是"分区 II：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="82780-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="82780-112">文档可在线获取;请参阅[ECMA C# 和通用语言基础结构标准和](../../../standard/components.md#applicable-standards)[标准 ECMA-335 - 通用语言基础结构 （CLI）。](http://www.ecma-international.org/publications/standards/Ecma-335.htm)</span><span class="sxs-lookup"><span data-stu-id="82780-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82780-113">要求</span><span class="sxs-lookup"><span data-stu-id="82780-113">Requirements</span></span>  
 <span data-ttu-id="82780-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82780-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82780-115">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="82780-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82780-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="82780-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82780-117">**.NET 框架版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82780-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82780-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82780-118">See also</span></span>

- [<span data-ttu-id="82780-119">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="82780-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="82780-120">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="82780-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
