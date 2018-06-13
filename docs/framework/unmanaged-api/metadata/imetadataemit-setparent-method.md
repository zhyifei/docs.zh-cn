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
ms.openlocfilehash: fdaa6aab28eb82450db7b9f946e033bfad55faf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446064"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="00146-102">IMetaDataEmit::SetParent 方法</span><span class="sxs-lookup"><span data-stu-id="00146-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="00146-103">建立的指定的成员定义的调用[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)，是通过调用定义的指定的类型、 成员[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="00146-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00146-104">语法</span><span class="sxs-lookup"><span data-stu-id="00146-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00146-105">参数</span><span class="sxs-lookup"><span data-stu-id="00146-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="00146-106">[in]`mdMemberRef`要接收新的父标记。</span><span class="sxs-lookup"><span data-stu-id="00146-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="00146-107">[in]`mdToken`新父级。</span><span class="sxs-lookup"><span data-stu-id="00146-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00146-108">要求</span><span class="sxs-lookup"><span data-stu-id="00146-108">Requirements</span></span>  
 <span data-ttu-id="00146-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00146-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00146-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="00146-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00146-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="00146-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00146-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00146-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00146-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="00146-113">See Also</span></span>  
 [<span data-ttu-id="00146-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="00146-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="00146-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="00146-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
