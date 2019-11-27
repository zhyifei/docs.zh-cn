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
ms.openlocfilehash: 44ae2d16563220f8f5b81b6f609dee7df715fd0e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447391"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="97cf4-102">IMetaDataTables::GetNextUserString 方法</span><span class="sxs-lookup"><span data-stu-id="97cf4-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="97cf4-103">获取包含当前表列中的下一个硬编码字符串的行的索引。</span><span class="sxs-lookup"><span data-stu-id="97cf4-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97cf4-104">语法</span><span class="sxs-lookup"><span data-stu-id="97cf4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97cf4-105">参数</span><span class="sxs-lookup"><span data-stu-id="97cf4-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="97cf4-106">中当前字符串列中的索引值。</span><span class="sxs-lookup"><span data-stu-id="97cf4-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="97cf4-107">弄指向列中下一个字符串的行索引的指针。</span><span class="sxs-lookup"><span data-stu-id="97cf4-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97cf4-108">备注</span><span class="sxs-lookup"><span data-stu-id="97cf4-108">Remarks</span></span>  
 <span data-ttu-id="97cf4-109">不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="97cf4-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="97cf4-110">有关 GUID 表的信息，请参阅公共语言基础结构（CLI）文档，尤其是 "第二部分：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="97cf4-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="97cf4-111">可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。</span><span class="sxs-lookup"><span data-stu-id="97cf4-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97cf4-112">要求</span><span class="sxs-lookup"><span data-stu-id="97cf4-112">Requirements</span></span>  
 <span data-ttu-id="97cf4-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97cf4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97cf4-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="97cf4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="97cf4-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="97cf4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="97cf4-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97cf4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97cf4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97cf4-117">See also</span></span>

- [<span data-ttu-id="97cf4-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="97cf4-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="97cf4-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="97cf4-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
