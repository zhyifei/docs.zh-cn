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
ms.openlocfilehash: ea617668a72413f3387a35fe009b37fa15d03354
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449603"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="e0a9c-102">IMetaDataTables::GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="e0a9c-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="e0a9c-103">获取名称、 行大小、 的行数，列数，并指定表的键列索引。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0a9c-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0a9c-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e0a9c-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0a9c-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="e0a9c-106">[in]表的标识符要返回其属性。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="e0a9c-107">[out]指向以字节为单位的表行的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="e0a9c-108">[out]指向表中的行数的指针。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="e0a9c-109">[out]指向表中的列数的指针。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="e0a9c-110">[out]指向的键列，则为-1 如果表没有键列的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="e0a9c-111">[out]指向表名的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0a9c-112">要求</span><span class="sxs-lookup"><span data-stu-id="e0a9c-112">Requirements</span></span>  
 <span data-ttu-id="e0a9c-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0a9c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0a9c-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e0a9c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0a9c-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e0a9c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0a9c-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0a9c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a9c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0a9c-117">See Also</span></span>  
 [<span data-ttu-id="e0a9c-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="e0a9c-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="e0a9c-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="e0a9c-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
