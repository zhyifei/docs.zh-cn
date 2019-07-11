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
ms.openlocfilehash: c6006c8892f650eec9528074d54f030d84ee8f88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750882"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="88300-102">IMetaDataEmit::SetParent 方法</span><span class="sxs-lookup"><span data-stu-id="88300-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="88300-103">建立指定的成员，定义的调用之前[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)，是指定类型的成员定义的调用之前[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="88300-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88300-104">语法</span><span class="sxs-lookup"><span data-stu-id="88300-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88300-105">参数</span><span class="sxs-lookup"><span data-stu-id="88300-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="88300-106">[in]`mdMemberRef`要接收新的父标记。</span><span class="sxs-lookup"><span data-stu-id="88300-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="88300-107">[in]`mdToken`新父级。</span><span class="sxs-lookup"><span data-stu-id="88300-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88300-108">要求</span><span class="sxs-lookup"><span data-stu-id="88300-108">Requirements</span></span>  
 <span data-ttu-id="88300-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88300-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88300-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="88300-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88300-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="88300-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88300-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88300-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88300-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="88300-113">See also</span></span>

- [<span data-ttu-id="88300-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="88300-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="88300-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="88300-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
