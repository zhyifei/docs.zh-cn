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
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175598"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="d4ee0-102">IMetaDataEmit::SetParent 方法</span><span class="sxs-lookup"><span data-stu-id="d4ee0-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="d4ee0-103">确定由之前对[IMetaDataEmit：:DefineOfRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)的调用定义的指定成员是指定类型的成员，由之前对[IMetaDataEmit：:DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)的调用定义。</span><span class="sxs-lookup"><span data-stu-id="d4ee0-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4ee0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4ee0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4ee0-105">parameters</span><span class="sxs-lookup"><span data-stu-id="d4ee0-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="d4ee0-106">[在]用于`mdMemberRef`接收新父项的令牌。</span><span class="sxs-lookup"><span data-stu-id="d4ee0-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="d4ee0-107">[在]为新`mdToken`父父的 。</span><span class="sxs-lookup"><span data-stu-id="d4ee0-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4ee0-108">要求</span><span class="sxs-lookup"><span data-stu-id="d4ee0-108">Requirements</span></span>  
 <span data-ttu-id="d4ee0-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ee0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4ee0-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="d4ee0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4ee0-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d4ee0-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4ee0-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4ee0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ee0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4ee0-113">See also</span></span>

- [<span data-ttu-id="d4ee0-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="d4ee0-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d4ee0-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="d4ee0-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
