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
ms.openlocfilehash: a73afaebc2943190eeeee50367ecd31f1fb59df1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432451"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="5b3d9-102">IMetaDataEmit::SetParent 方法</span><span class="sxs-lookup"><span data-stu-id="5b3d9-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="5b3d9-103">确定由之前调用[IMetaDataEmit：:D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)定义的指定成员是否为指定类型的成员，该成员由先前调用[IMetaDataEmit：:D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)定义。</span><span class="sxs-lookup"><span data-stu-id="5b3d9-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b3d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b3d9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b3d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b3d9-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="5b3d9-106">中用于接收新父级的 `mdMemberRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="5b3d9-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="5b3d9-107">中新父级的 `mdToken`。</span><span class="sxs-lookup"><span data-stu-id="5b3d9-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b3d9-108">要求</span><span class="sxs-lookup"><span data-stu-id="5b3d9-108">Requirements</span></span>  
 <span data-ttu-id="5b3d9-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b3d9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b3d9-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5b3d9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b3d9-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5b3d9-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b3d9-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b3d9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3d9-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b3d9-113">See also</span></span>

- [<span data-ttu-id="5b3d9-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="5b3d9-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5b3d9-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="5b3d9-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
