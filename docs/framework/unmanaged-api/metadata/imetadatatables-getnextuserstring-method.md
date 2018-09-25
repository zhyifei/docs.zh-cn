---
title: IMetaDataTables::GetNextUserString 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b326765e792bf97658d951a2d5590d22eff546
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157738"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="e8c70-102">IMetaDataTables::GetNextUserString 方法</span><span class="sxs-lookup"><span data-stu-id="e8c70-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="e8c70-103">获取包含在当前表列中的下一步的硬编码字符串的行的索引。</span><span class="sxs-lookup"><span data-stu-id="e8c70-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c70-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8c70-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8c70-105">参数</span><span class="sxs-lookup"><span data-stu-id="e8c70-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="e8c70-106">[in]从当前字符串列的索引值。</span><span class="sxs-lookup"><span data-stu-id="e8c70-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="e8c70-107">[out]一个指向下一个字符串列中的行索引。</span><span class="sxs-lookup"><span data-stu-id="e8c70-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8c70-108">备注</span><span class="sxs-lookup"><span data-stu-id="e8c70-108">Remarks</span></span>  
 <span data-ttu-id="e8c70-109">不建议使用此方法，因为它不会返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="e8c70-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="e8c70-110">GUID 表有关的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"分区 II:: 元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="e8c70-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="e8c70-111">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="e8c70-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8c70-112">要求</span><span class="sxs-lookup"><span data-stu-id="e8c70-112">Requirements</span></span>  
 <span data-ttu-id="e8c70-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8c70-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8c70-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8c70-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8c70-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e8c70-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8c70-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8c70-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c70-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8c70-117">See Also</span></span>  
 [<span data-ttu-id="e8c70-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="e8c70-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="e8c70-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="e8c70-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
