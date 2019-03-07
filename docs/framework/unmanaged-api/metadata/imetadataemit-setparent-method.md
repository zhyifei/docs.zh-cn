---
title: IMetaDataEmit::SetParent 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f025bf8f6e71192ca128f8c9908780a159700757
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482192"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="3ec55-102">IMetaDataEmit::SetParent 方法</span><span class="sxs-lookup"><span data-stu-id="3ec55-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="3ec55-103">建立指定的成员，定义的调用之前[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)，是指定类型的成员定义的调用之前[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec55-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ec55-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ec55-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ec55-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ec55-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="3ec55-106">[in]`mdMemberRef`要接收新的父标记。</span><span class="sxs-lookup"><span data-stu-id="3ec55-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="3ec55-107">[in]`mdToken`新父级。</span><span class="sxs-lookup"><span data-stu-id="3ec55-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ec55-108">要求</span><span class="sxs-lookup"><span data-stu-id="3ec55-108">Requirements</span></span>  
 <span data-ttu-id="3ec55-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec55-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ec55-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3ec55-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ec55-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3ec55-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ec55-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ec55-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec55-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ec55-113">See also</span></span>
- [<span data-ttu-id="3ec55-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="3ec55-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3ec55-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="3ec55-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
