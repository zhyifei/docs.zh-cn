---
title: IMetaDataTables::GetColumnInfo 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6156499368fb743b69c03f38b40ad3c5bcabce6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174897"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="1ea05-102">IMetaDataTables::GetColumnInfo 方法</span><span class="sxs-lookup"><span data-stu-id="1ea05-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="1ea05-103">指定表中获取有关指定的列的数据。</span><span class="sxs-lookup"><span data-stu-id="1ea05-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ea05-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ea05-104">Syntax</span></span>  
  
```  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ea05-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ea05-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="1ea05-106">[in]所需的表的索引。</span><span class="sxs-lookup"><span data-stu-id="1ea05-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="1ea05-107">[in]所需的列的索引。</span><span class="sxs-lookup"><span data-stu-id="1ea05-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="1ea05-108">[out]指向的行中列的偏移量的指针。</span><span class="sxs-lookup"><span data-stu-id="1ea05-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="1ea05-109">[out]指向大小 （字节） 列的指针。</span><span class="sxs-lookup"><span data-stu-id="1ea05-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="1ea05-110">[out]指向的列中值的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="1ea05-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="1ea05-111">[out]为列名称的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="1ea05-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ea05-112">要求</span><span class="sxs-lookup"><span data-stu-id="1ea05-112">Requirements</span></span>  
 <span data-ttu-id="1ea05-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea05-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ea05-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1ea05-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ea05-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1ea05-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ea05-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ea05-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea05-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ea05-117">See also</span></span>

- [<span data-ttu-id="1ea05-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="1ea05-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="1ea05-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="1ea05-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
