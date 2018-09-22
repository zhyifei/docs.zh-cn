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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f589225dde1ba2aabc4ca32542339a771c3287d4
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46568749"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="00277-102">IMetaDataTables::GetGuid 方法</span><span class="sxs-lookup"><span data-stu-id="00277-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="00277-103">获取从指定索引处的行的 GUID。</span><span class="sxs-lookup"><span data-stu-id="00277-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00277-104">语法</span><span class="sxs-lookup"><span data-stu-id="00277-104">Syntax</span></span>  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00277-105">参数</span><span class="sxs-lookup"><span data-stu-id="00277-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="00277-106">[in]要从其中获取 GUID 的行的索引。</span><span class="sxs-lookup"><span data-stu-id="00277-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="00277-107">[out]指向 GUID 的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="00277-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00277-108">备注</span><span class="sxs-lookup"><span data-stu-id="00277-108">Remarks</span></span>  
 <span data-ttu-id="00277-109">不建议使用此方法，因为它不会返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="00277-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="00277-110">GUID 表有关的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"分区 II:: 元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="00277-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="00277-111">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="00277-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00277-112">要求</span><span class="sxs-lookup"><span data-stu-id="00277-112">Requirements</span></span>  
 <span data-ttu-id="00277-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00277-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00277-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="00277-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00277-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="00277-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00277-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00277-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00277-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="00277-117">See Also</span></span>  
 [<span data-ttu-id="00277-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="00277-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="00277-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="00277-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
