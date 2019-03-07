---
title: IMetaDataTables::GetTableInfo 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 876f74d7fe7555f71db0bd77e68f657dfc80b179
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478955"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="3c852-102">IMetaDataTables::GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3c852-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="3c852-103">获取名称、 行大小、 行数、 列数和指定的表的键列索引。</span><span class="sxs-lookup"><span data-stu-id="3c852-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c852-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c852-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c852-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c852-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="3c852-106">[in]表的标识符要返回其属性。</span><span class="sxs-lookup"><span data-stu-id="3c852-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="3c852-107">[out]指向大小 （字节） 的表行的指针。</span><span class="sxs-lookup"><span data-stu-id="3c852-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="3c852-108">[out]指向表中的行数的指针。</span><span class="sxs-lookup"><span data-stu-id="3c852-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="3c852-109">[out]指向表中的列数的指针。</span><span class="sxs-lookup"><span data-stu-id="3c852-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="3c852-110">[out]索引键列，则为-1 如果表没有键列的指针。</span><span class="sxs-lookup"><span data-stu-id="3c852-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="3c852-111">[out]为表名的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="3c852-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c852-112">要求</span><span class="sxs-lookup"><span data-stu-id="3c852-112">Requirements</span></span>  
 <span data-ttu-id="3c852-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c852-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c852-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c852-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c852-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3c852-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c852-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c852-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c852-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c852-117">See also</span></span>
- [<span data-ttu-id="3c852-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="3c852-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="3c852-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="3c852-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
