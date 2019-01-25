---
title: IMetaDataTables::GetNextGuid 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e23026241a836bfa6cf6f186a47037370c174e61
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680931"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="833c0-102">IMetaDataTables::GetNextGuid 方法</span><span class="sxs-lookup"><span data-stu-id="833c0-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="833c0-103">获取当前表的列中的下一步的 GUID 值的索引。</span><span class="sxs-lookup"><span data-stu-id="833c0-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="833c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="833c0-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="833c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="833c0-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="833c0-106">[in]GUID 的表列中的索引值。</span><span class="sxs-lookup"><span data-stu-id="833c0-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="833c0-107">[out]一个指向下一步的 GUID 值的索引。</span><span class="sxs-lookup"><span data-stu-id="833c0-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="833c0-108">备注</span><span class="sxs-lookup"><span data-stu-id="833c0-108">Remarks</span></span>  
 <span data-ttu-id="833c0-109">不建议使用此方法，因为它不会返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="833c0-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="833c0-110">有关 GUID 表的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"第二部分：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="833c0-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="833c0-111">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="833c0-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="833c0-112">要求</span><span class="sxs-lookup"><span data-stu-id="833c0-112">Requirements</span></span>  
 <span data-ttu-id="833c0-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="833c0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="833c0-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="833c0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="833c0-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="833c0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="833c0-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="833c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="833c0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="833c0-117">See also</span></span>
- [<span data-ttu-id="833c0-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="833c0-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="833c0-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="833c0-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
