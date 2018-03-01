---
title: "IMetaDataTables::GetTableInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ce9e3beb15724c7d7ddf02cbe7f83795d474139
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="598bc-102">IMetaDataTables::GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="598bc-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="598bc-103">获取名称、 行大小、 的行数，列数，并指定表的键列索引。</span><span class="sxs-lookup"><span data-stu-id="598bc-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="598bc-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="598bc-105">参数</span><span class="sxs-lookup"><span data-stu-id="598bc-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="598bc-106">[in]表的标识符要返回其属性。</span><span class="sxs-lookup"><span data-stu-id="598bc-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="598bc-107">[out]指向以字节为单位的表行的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="598bc-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="598bc-108">[out]指向表中的行数的指针。</span><span class="sxs-lookup"><span data-stu-id="598bc-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="598bc-109">[out]指向表中的列数的指针。</span><span class="sxs-lookup"><span data-stu-id="598bc-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="598bc-110">[out]指向的键列，则为-1 如果表没有键列的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="598bc-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="598bc-111">[out]指向表名的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="598bc-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="598bc-112">惠?</span><span class="sxs-lookup"><span data-stu-id="598bc-112">Requirements</span></span>  
 <span data-ttu-id="598bc-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="598bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="598bc-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="598bc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="598bc-115">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="598bc-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="598bc-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="598bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598bc-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="598bc-117">See Also</span></span>  
 [<span data-ttu-id="598bc-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="598bc-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="598bc-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="598bc-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
