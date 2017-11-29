---
title: "IMetaDataTables::GetString 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 687380d3a09a80db216aafbf1ee84c76e31bbf36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="dd77e-102">IMetaDataTables::GetString 方法</span><span class="sxs-lookup"><span data-stu-id="dd77e-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="dd77e-103">获取当前引用作用域中从表的列的指定索引处的字符串。</span><span class="sxs-lookup"><span data-stu-id="dd77e-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd77e-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd77e-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd77e-105">参数</span><span class="sxs-lookup"><span data-stu-id="dd77e-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="dd77e-106">[in]若要开始搜索下一个值处的索引。</span><span class="sxs-lookup"><span data-stu-id="dd77e-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="dd77e-107">[out]指向返回的字符串值的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="dd77e-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd77e-108">要求</span><span class="sxs-lookup"><span data-stu-id="dd77e-108">Requirements</span></span>  
 <span data-ttu-id="dd77e-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd77e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd77e-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd77e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd77e-111">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dd77e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd77e-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd77e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd77e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd77e-113">See Also</span></span>  
 [<span data-ttu-id="dd77e-114">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="dd77e-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="dd77e-115">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="dd77e-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
