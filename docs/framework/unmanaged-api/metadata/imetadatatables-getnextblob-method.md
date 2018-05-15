---
title: IMetaDataTables::GetNextBlob 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caf7faeea4bcec9b73f3c43f0923d308baebf6d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="40dfb-102">IMetaDataTables::GetNextBlob 方法</span><span class="sxs-lookup"><span data-stu-id="40dfb-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="40dfb-103">获取表中的下一步二进制大型对象 (BLOB) 的索引。</span><span class="sxs-lookup"><span data-stu-id="40dfb-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40dfb-104">语法</span><span class="sxs-lookup"><span data-stu-id="40dfb-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40dfb-105">参数</span><span class="sxs-lookup"><span data-stu-id="40dfb-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="40dfb-106">[in]返回的 Blob 列的索引。</span><span class="sxs-lookup"><span data-stu-id="40dfb-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="40dfb-107">[out]指向下一个 BLOB 的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="40dfb-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40dfb-108">要求</span><span class="sxs-lookup"><span data-stu-id="40dfb-108">Requirements</span></span>  
 <span data-ttu-id="40dfb-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40dfb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40dfb-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="40dfb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40dfb-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="40dfb-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40dfb-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40dfb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40dfb-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="40dfb-113">See Also</span></span>  
 [<span data-ttu-id="40dfb-114">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="40dfb-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="40dfb-115">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="40dfb-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
