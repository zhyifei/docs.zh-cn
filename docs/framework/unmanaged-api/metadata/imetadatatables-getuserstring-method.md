---
title: "IMetaDataTables::GetUserString 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 648cc9e6f947f5eaf5dd6c9354ba305f7ca0d530
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="5f4b9-102">IMetaDataTables::GetUserString 方法</span><span class="sxs-lookup"><span data-stu-id="5f4b9-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="5f4b9-103">获取当前范围中的字符串列中的指定索引处的硬编码字符串。</span><span class="sxs-lookup"><span data-stu-id="5f4b9-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f4b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f4b9-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f4b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f4b9-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="5f4b9-106">[in]将从中检索硬编码字符串的索引值。</span><span class="sxs-lookup"><span data-stu-id="5f4b9-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="5f4b9-107">[out]P; 的大小的 ointer `ppData`。</span><span class="sxs-lookup"><span data-stu-id="5f4b9-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="5f4b9-108">[out]指向返回的字符串的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="5f4b9-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f4b9-109">要求</span><span class="sxs-lookup"><span data-stu-id="5f4b9-109">Requirements</span></span>  
 <span data-ttu-id="5f4b9-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f4b9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f4b9-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f4b9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f4b9-112">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5f4b9-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f4b9-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f4b9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4b9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f4b9-114">See Also</span></span>  
 [<span data-ttu-id="5f4b9-115">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="5f4b9-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="5f4b9-116">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="5f4b9-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
