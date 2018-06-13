---
title: IMetaDataTables::GetTableIndex 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d207eae5e9ac1b3020216226442321e72840c037
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450357"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="4e960-102">IMetaDataTables::GetTableIndex 方法</span><span class="sxs-lookup"><span data-stu-id="4e960-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="4e960-103">获取指定标记所引用的表的索引。</span><span class="sxs-lookup"><span data-stu-id="4e960-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e960-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e960-104">Syntax</span></span>  
  
```  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e960-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e960-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="4e960-106">[in]引用表中的令牌。</span><span class="sxs-lookup"><span data-stu-id="4e960-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="4e960-107">[out]指向所引用的表返回的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="4e960-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e960-108">备注</span><span class="sxs-lookup"><span data-stu-id="4e960-108">Remarks</span></span>  
 <span data-ttu-id="4e960-109">不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="4e960-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="4e960-110">GUID 表有关的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"第 ii 部分： 元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="4e960-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="4e960-111">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](http://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="4e960-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e960-112">要求</span><span class="sxs-lookup"><span data-stu-id="4e960-112">Requirements</span></span>  
 <span data-ttu-id="4e960-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e960-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e960-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4e960-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e960-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4e960-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e960-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e960-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e960-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e960-117">See Also</span></span>  
 [<span data-ttu-id="4e960-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="4e960-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="4e960-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="4e960-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
