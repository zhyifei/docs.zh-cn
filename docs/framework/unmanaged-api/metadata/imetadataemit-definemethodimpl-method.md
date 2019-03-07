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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3a6f98dca1c6665b312384721a8fb590f914175
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468892"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="7f264-102">IMetaDataEmit::DefineMethodImpl 方法</span><span class="sxs-lookup"><span data-stu-id="7f264-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="7f264-103">创建继承自一个接口，方法的实现的定义，并将令牌返回到该方法实现定义。</span><span class="sxs-lookup"><span data-stu-id="7f264-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f264-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f264-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f264-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f264-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="7f264-106">[in]`mdTypedef`令牌的实现类。</span><span class="sxs-lookup"><span data-stu-id="7f264-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="7f264-107">[in]`mdMethodDef`或`mdMethodRef`令牌的代码体。</span><span class="sxs-lookup"><span data-stu-id="7f264-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="7f264-108">[in]`mdMethodDef`或`mdMethodRef`正在实现的接口方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="7f264-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f264-109">要求</span><span class="sxs-lookup"><span data-stu-id="7f264-109">Requirements</span></span>  
 <span data-ttu-id="7f264-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f264-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f264-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7f264-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f264-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7f264-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f264-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f264-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f264-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f264-114">See also</span></span>
- [<span data-ttu-id="7f264-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="7f264-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7f264-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="7f264-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
