---
title: "IMetaDataTables::GetCodedTokenInfo 方法"
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
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 72c88751940da16a691a5eae46507986a50904a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="afb1a-102">IMetaDataTables::GetCodedTokenInfo 方法</span><span class="sxs-lookup"><span data-stu-id="afb1a-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="afb1a-103">获取一个指向与指定的行索引关联的标记数组。</span><span class="sxs-lookup"><span data-stu-id="afb1a-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb1a-104">语法</span><span class="sxs-lookup"><span data-stu-id="afb1a-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="afb1a-105">参数</span><span class="sxs-lookup"><span data-stu-id="afb1a-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="afb1a-106">[in]编码的令牌要返回的类型。</span><span class="sxs-lookup"><span data-stu-id="afb1a-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="afb1a-107">[out]长度的指针`ppTokens`。</span><span class="sxs-lookup"><span data-stu-id="afb1a-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="afb1a-108">[out]指向包含返回的令牌的列表的数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="afb1a-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="afb1a-109">[out]指针到指向在令牌的名称`ixCdTkn`。</span><span class="sxs-lookup"><span data-stu-id="afb1a-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afb1a-110">惠?</span><span class="sxs-lookup"><span data-stu-id="afb1a-110">Requirements</span></span>  
 <span data-ttu-id="afb1a-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="afb1a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afb1a-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="afb1a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="afb1a-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="afb1a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="afb1a-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afb1a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb1a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="afb1a-115">See Also</span></span>  
 [<span data-ttu-id="afb1a-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="afb1a-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="afb1a-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="afb1a-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
