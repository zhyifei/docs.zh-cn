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
ms.openlocfilehash: a02719651d8169c1122f5a46b1b8df39b28612ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779790"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="7410b-102">IMetaDataTables::GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="7410b-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="7410b-103">获取指定的行索引处，在指定的表索引的表中的行。</span><span class="sxs-lookup"><span data-stu-id="7410b-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7410b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7410b-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7410b-105">参数</span><span class="sxs-lookup"><span data-stu-id="7410b-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="7410b-106">[in]将从其检索行的表的索引。</span><span class="sxs-lookup"><span data-stu-id="7410b-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="7410b-107">[in]若要获取的行的索引。</span><span class="sxs-lookup"><span data-stu-id="7410b-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="7410b-108">[out]指向行的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="7410b-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7410b-109">备注</span><span class="sxs-lookup"><span data-stu-id="7410b-109">Remarks</span></span>  
 <span data-ttu-id="7410b-110">不建议使用此方法，因为它不会返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="7410b-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="7410b-111">有关 GUID 表的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"第二部分：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="7410b-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="7410b-112">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="7410b-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7410b-113">要求</span><span class="sxs-lookup"><span data-stu-id="7410b-113">Requirements</span></span>  
 <span data-ttu-id="7410b-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7410b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7410b-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7410b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7410b-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7410b-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7410b-117">**.NET framework 版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7410b-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7410b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7410b-118">See also</span></span>

- [<span data-ttu-id="7410b-119">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="7410b-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="7410b-120">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="7410b-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
