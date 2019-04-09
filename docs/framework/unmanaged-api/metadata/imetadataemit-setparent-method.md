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
ms.openlocfilehash: fe27d8a0508a13c1f54eef00d5119bec4daec4a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140434"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="c54fc-102">IMetaDataEmit::SetParent 方法</span><span class="sxs-lookup"><span data-stu-id="c54fc-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="c54fc-103">建立指定的成员，定义的调用之前[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)，是指定类型的成员定义的调用之前[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c54fc-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c54fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c54fc-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c54fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="c54fc-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="c54fc-106">[in]`mdMemberRef`要接收新的父标记。</span><span class="sxs-lookup"><span data-stu-id="c54fc-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="c54fc-107">[in]`mdToken`新父级。</span><span class="sxs-lookup"><span data-stu-id="c54fc-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c54fc-108">要求</span><span class="sxs-lookup"><span data-stu-id="c54fc-108">Requirements</span></span>  
 <span data-ttu-id="c54fc-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c54fc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c54fc-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c54fc-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c54fc-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c54fc-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c54fc-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c54fc-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c54fc-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c54fc-113">See also</span></span>

- [<span data-ttu-id="c54fc-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="c54fc-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c54fc-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="c54fc-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
