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
ms.openlocfilehash: 9bf3e5d427698673576f71e290fde54275b75317
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683451"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="cbe2d-102">IMetaDataTables::GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="cbe2d-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="cbe2d-103">获取名称、 行大小、 行数、 列数和指定的表的键列索引。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="cbe2d-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="cbe2d-105">参数</span><span class="sxs-lookup"><span data-stu-id="cbe2d-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="cbe2d-106">[in]表的标识符要返回其属性。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="cbe2d-107">[out]指向大小 （字节） 的表行的指针。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="cbe2d-108">[out]指向表中的行数的指针。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="cbe2d-109">[out]指向表中的列数的指针。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="cbe2d-110">[out]索引键列，则为-1 如果表没有键列的指针。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="cbe2d-111">[out]为表名的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe2d-112">要求</span><span class="sxs-lookup"><span data-stu-id="cbe2d-112">Requirements</span></span>  
 <span data-ttu-id="cbe2d-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbe2d-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cbe2d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbe2d-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cbe2d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbe2d-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe2d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe2d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe2d-117">See also</span></span>
- [<span data-ttu-id="cbe2d-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="cbe2d-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cbe2d-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="cbe2d-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
