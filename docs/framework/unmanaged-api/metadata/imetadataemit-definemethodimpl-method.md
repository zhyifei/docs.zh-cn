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
ms.openlocfilehash: 2ab66fecfaa66b5c56690950f6b19ecfd7e85e33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443984"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="0eda2-102">IMetaDataEmit::DefineMethodImpl 方法</span><span class="sxs-lookup"><span data-stu-id="0eda2-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="0eda2-103">创建实现接口，从继承的方法的定义，并返回到该方法实现定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="0eda2-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eda2-104">语法</span><span class="sxs-lookup"><span data-stu-id="0eda2-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0eda2-105">参数</span><span class="sxs-lookup"><span data-stu-id="0eda2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0eda2-106">[in]`mdTypedef`令牌的实现的类。</span><span class="sxs-lookup"><span data-stu-id="0eda2-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="0eda2-107">[in]`mdMethodDef`或`mdMethodRef`令牌的代码体。</span><span class="sxs-lookup"><span data-stu-id="0eda2-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="0eda2-108">[in]`mdMethodDef`或`mdMethodRef`正在实现的接口方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="0eda2-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eda2-109">要求</span><span class="sxs-lookup"><span data-stu-id="0eda2-109">Requirements</span></span>  
 <span data-ttu-id="0eda2-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0eda2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eda2-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0eda2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0eda2-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0eda2-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0eda2-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eda2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eda2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eda2-114">See Also</span></span>  
 [<span data-ttu-id="0eda2-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="0eda2-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0eda2-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="0eda2-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
