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
ms.openlocfilehash: 9973ef77a064dfe144d742d8cf12d8ae8dd2565f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447409"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="b316e-102">IMetaDataTables::GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="b316e-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="b316e-103">获取位于指定表索引处的表中指定行索引处的行。</span><span class="sxs-lookup"><span data-stu-id="b316e-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b316e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b316e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b316e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b316e-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="b316e-106">中要从中检索行的表的索引。</span><span class="sxs-lookup"><span data-stu-id="b316e-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="b316e-107">中要获取的行的索引。</span><span class="sxs-lookup"><span data-stu-id="b316e-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="b316e-108">弄指向指向行的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b316e-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b316e-109">备注</span><span class="sxs-lookup"><span data-stu-id="b316e-109">Remarks</span></span>  
 <span data-ttu-id="b316e-110">不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="b316e-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="b316e-111">有关 GUID 表的信息，请参阅公共语言基础结构（CLI）文档，尤其是 "第二部分：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="b316e-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="b316e-112">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="b316e-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b316e-113">要求</span><span class="sxs-lookup"><span data-stu-id="b316e-113">Requirements</span></span>  
 <span data-ttu-id="b316e-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b316e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b316e-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b316e-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b316e-116">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b316e-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b316e-117">**.NET Framework 版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b316e-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b316e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b316e-118">See also</span></span>

- [<span data-ttu-id="b316e-119">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="b316e-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b316e-120">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="b316e-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
