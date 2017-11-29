---
title: "IMetaDataEmit::DeleteToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeleteToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7dd96cff41ff43a048aa50d00dbdf9d1fab88e72
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="711ee-102">IMetaDataEmit::DeleteToken 方法</span><span class="sxs-lookup"><span data-stu-id="711ee-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="711ee-103">从当前的元数据范围中删除指定的标记。</span><span class="sxs-lookup"><span data-stu-id="711ee-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="711ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="711ee-104">Syntax</span></span>  
  
```  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="711ee-105">参数</span><span class="sxs-lookup"><span data-stu-id="711ee-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="711ee-106">[in]要删除的标记。</span><span class="sxs-lookup"><span data-stu-id="711ee-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="711ee-107">要求</span><span class="sxs-lookup"><span data-stu-id="711ee-107">Requirements</span></span>  
 <span data-ttu-id="711ee-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="711ee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="711ee-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="711ee-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="711ee-110">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="711ee-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="711ee-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="711ee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711ee-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="711ee-112">See Also</span></span>  
 [<span data-ttu-id="711ee-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="711ee-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="711ee-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="711ee-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
