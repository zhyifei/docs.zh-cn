---
title: "IMetaDataEmit::SetParent 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetParent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56436b3801eb55559605f6c875bb6fde84c2db8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="df83f-102">IMetaDataEmit::SetParent 方法</span><span class="sxs-lookup"><span data-stu-id="df83f-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="df83f-103">建立的指定的成员定义的调用[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)，是通过调用定义的指定的类型、 成员[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="df83f-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df83f-104">语法</span><span class="sxs-lookup"><span data-stu-id="df83f-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df83f-105">参数</span><span class="sxs-lookup"><span data-stu-id="df83f-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="df83f-106">[in]`mdMemberRef`要接收新的父标记。</span><span class="sxs-lookup"><span data-stu-id="df83f-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="df83f-107">[in]`mdToken`新父级。</span><span class="sxs-lookup"><span data-stu-id="df83f-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df83f-108">要求</span><span class="sxs-lookup"><span data-stu-id="df83f-108">Requirements</span></span>  
 <span data-ttu-id="df83f-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df83f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df83f-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df83f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df83f-111">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="df83f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df83f-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df83f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df83f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df83f-113">See Also</span></span>  
 [<span data-ttu-id="df83f-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="df83f-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="df83f-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="df83f-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
