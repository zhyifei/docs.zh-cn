---
title: "IMetaDataEmit::DefineUserString 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eb3e21e88da8fec08acf1ecbe451c5914b6cccaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="4c9ae-102">IMetaDataEmit::DefineUserString 方法</span><span class="sxs-lookup"><span data-stu-id="4c9ae-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="4c9ae-103">获取指定的文字字符串的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4c9ae-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c9ae-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c9ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c9ae-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="4c9ae-106">[in]要存储的用户字符串。</span><span class="sxs-lookup"><span data-stu-id="4c9ae-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="4c9ae-107">[in]中的宽字符计数`szString`。</span><span class="sxs-lookup"><span data-stu-id="4c9ae-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="4c9ae-108">[out]分配字符串标记。</span><span class="sxs-lookup"><span data-stu-id="4c9ae-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c9ae-109">要求</span><span class="sxs-lookup"><span data-stu-id="4c9ae-109">Requirements</span></span>  
 <span data-ttu-id="4c9ae-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c9ae-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4c9ae-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c9ae-112">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4c9ae-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c9ae-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c9ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9ae-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c9ae-114">See Also</span></span>  
 [<span data-ttu-id="4c9ae-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="4c9ae-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="4c9ae-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="4c9ae-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
