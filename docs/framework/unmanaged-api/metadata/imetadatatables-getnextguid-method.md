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
ms.openlocfilehash: d4055975287267d08d2c2224ff6ddaa39fca548d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937796"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="5cdff-102">IMetaDataTables::GetNextGuid 方法</span><span class="sxs-lookup"><span data-stu-id="5cdff-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="5cdff-103">获取当前表列中的下一个 GUID 值的索引。</span><span class="sxs-lookup"><span data-stu-id="5cdff-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cdff-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cdff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cdff-105">参数</span><span class="sxs-lookup"><span data-stu-id="5cdff-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="5cdff-106">中来自 GUID 表列的索引值。</span><span class="sxs-lookup"><span data-stu-id="5cdff-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="5cdff-107">弄指向下一个 GUID 值的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="5cdff-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cdff-108">备注</span><span class="sxs-lookup"><span data-stu-id="5cdff-108">Remarks</span></span>  

  <span data-ttu-id="5cdff-109">不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="5cdff-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="5cdff-110">有关 GUID 表的信息，请参阅公共语言基础结构（CLI）文档，尤其是 "第二部分：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="5cdff-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="5cdff-111">文档在线提供;请[参阅C# ECMA 和公共语言基础结构标准](../../../standard/components.md#applicable-standards)和[标准 ECMA-335-公共语言基础结构（CLI）](http://www.ecma-international.org/publications/standards/Ecma-335.htm)。</span><span class="sxs-lookup"><span data-stu-id="5cdff-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cdff-112">需求</span><span class="sxs-lookup"><span data-stu-id="5cdff-112">Requirements</span></span>  
 <span data-ttu-id="5cdff-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5cdff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cdff-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5cdff-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cdff-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5cdff-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5cdff-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cdff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cdff-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cdff-117">See also</span></span>

- [<span data-ttu-id="5cdff-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="5cdff-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5cdff-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="5cdff-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
