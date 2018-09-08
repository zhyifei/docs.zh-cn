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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d24dbcbdd8b0ed0736f7b59564cf72dffaa5a8f8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44196707"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="05d01-102">IMetaDataTables::GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="05d01-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="05d01-103">获取指定的行索引处，在指定的表索引的表中的行。</span><span class="sxs-lookup"><span data-stu-id="05d01-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d01-104">语法</span><span class="sxs-lookup"><span data-stu-id="05d01-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05d01-105">参数</span><span class="sxs-lookup"><span data-stu-id="05d01-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="05d01-106">[in]将从其检索行的表的索引。</span><span class="sxs-lookup"><span data-stu-id="05d01-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="05d01-107">[in]若要获取的行的索引。</span><span class="sxs-lookup"><span data-stu-id="05d01-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="05d01-108">[out]指向行的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="05d01-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05d01-109">备注</span><span class="sxs-lookup"><span data-stu-id="05d01-109">Remarks</span></span>  
 <span data-ttu-id="05d01-110">不建议使用此方法，因为它不会返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="05d01-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="05d01-111">GUID 表有关的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"分区 II:: 元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="05d01-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="05d01-112">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="05d01-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d01-113">要求</span><span class="sxs-lookup"><span data-stu-id="05d01-113">Requirements</span></span>  
 <span data-ttu-id="05d01-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05d01-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d01-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05d01-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05d01-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="05d01-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05d01-117">**.NET framework 版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d01-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d01-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="05d01-118">See Also</span></span>  
 [<span data-ttu-id="05d01-119">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="05d01-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="05d01-120">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="05d01-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
