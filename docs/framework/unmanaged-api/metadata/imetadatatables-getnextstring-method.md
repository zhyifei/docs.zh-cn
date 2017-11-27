---
title: "IMetaDataTables::GetNextString 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9d9062ef164c5a50652ed78786725967fda999d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="15d52-102">IMetaDataTables::GetNextString 方法</span><span class="sxs-lookup"><span data-stu-id="15d52-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="15d52-103">获取当前的表列中的下一步的字符串的索引。</span><span class="sxs-lookup"><span data-stu-id="15d52-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15d52-104">语法</span><span class="sxs-lookup"><span data-stu-id="15d52-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15d52-105">参数</span><span class="sxs-lookup"><span data-stu-id="15d52-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="15d52-106">[in]字符串表列中的索引值。</span><span class="sxs-lookup"><span data-stu-id="15d52-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="15d52-107">[out]指向列中的下一步字符串的索引的指针。</span><span class="sxs-lookup"><span data-stu-id="15d52-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15d52-108">要求</span><span class="sxs-lookup"><span data-stu-id="15d52-108">Requirements</span></span>  
 <span data-ttu-id="15d52-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15d52-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15d52-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15d52-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15d52-111">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="15d52-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15d52-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15d52-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d52-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15d52-113">See Also</span></span>  
 [<span data-ttu-id="15d52-114">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="15d52-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="15d52-115">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="15d52-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
