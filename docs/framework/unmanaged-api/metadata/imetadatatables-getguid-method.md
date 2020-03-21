---
title: IMetaDataTables::GetGuid 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 57df124f15f78daad053d9634e1baa969a65cc35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175273"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="f17d2-102">IMetaDataTables::GetGuid 方法</span><span class="sxs-lookup"><span data-stu-id="f17d2-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="f17d2-103">从指定索引处的行获取 GUID。</span><span class="sxs-lookup"><span data-stu-id="f17d2-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="f17d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f17d2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f17d2-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="f17d2-106">[在]要从中获取 GUID 的行的索引。</span><span class="sxs-lookup"><span data-stu-id="f17d2-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="f17d2-107">[出]指向 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="f17d2-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f17d2-108">备注</span><span class="sxs-lookup"><span data-stu-id="f17d2-108">Remarks</span></span>  

  <span data-ttu-id="f17d2-109">我们不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="f17d2-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f17d2-110">有关 GUID 表的信息，请参阅通用语言基础结构 （CLI） 文档，尤其是"分区 II：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="f17d2-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f17d2-111">文档可在线获取;请参阅[ECMA C# 和通用语言基础结构标准和](../../../standard/components.md#applicable-standards)[标准 ECMA-335 - 通用语言基础结构 （CLI）。](http://www.ecma-international.org/publications/standards/Ecma-335.htm)</span><span class="sxs-lookup"><span data-stu-id="f17d2-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f17d2-112">要求</span><span class="sxs-lookup"><span data-stu-id="f17d2-112">Requirements</span></span>  
 <span data-ttu-id="f17d2-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f17d2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f17d2-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="f17d2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f17d2-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f17d2-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f17d2-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f17d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17d2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f17d2-117">See also</span></span>

- [<span data-ttu-id="f17d2-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="f17d2-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="f17d2-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="f17d2-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
