---
title: IMetaDataEmit::DefineMethodImpl 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
ms.openlocfilehash: 64d76efa8c2f29fda559e5c84217b865540027ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175819"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="e9089-102">IMetaDataEmit::DefineMethodImpl 方法</span><span class="sxs-lookup"><span data-stu-id="e9089-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="e9089-103">为从接口继承的方法的实现创建定义，并将令牌返回到该方法实现定义。</span><span class="sxs-lookup"><span data-stu-id="e9089-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9089-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9089-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9089-105">parameters</span><span class="sxs-lookup"><span data-stu-id="e9089-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e9089-106">[在]实现`mdTypedef`类的令牌。</span><span class="sxs-lookup"><span data-stu-id="e9089-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="e9089-107">[在]代码`mdMethodDef`正文`mdMemberRef`的 或 令牌。</span><span class="sxs-lookup"><span data-stu-id="e9089-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="e9089-108">[在]正在`mdMethodDef`实现的`mdMemberRef`接口方法的 或 令牌。</span><span class="sxs-lookup"><span data-stu-id="e9089-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9089-109">要求</span><span class="sxs-lookup"><span data-stu-id="e9089-109">Requirements</span></span>  
 <span data-ttu-id="e9089-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9089-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9089-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="e9089-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9089-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e9089-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9089-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9089-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9089-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9089-114">See also</span></span>

- [<span data-ttu-id="e9089-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="e9089-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e9089-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="e9089-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
