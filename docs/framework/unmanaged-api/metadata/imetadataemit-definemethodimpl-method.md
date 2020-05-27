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
ms.openlocfilehash: 5ed5afbbf49b6680d00e78b6af3d45c6f0a7229d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004486"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="0050a-102">IMetaDataEmit::DefineMethodImpl 方法</span><span class="sxs-lookup"><span data-stu-id="0050a-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="0050a-103">创建一个定义，用于实现从接口继承的方法，并返回该方法实现定义的标记。</span><span class="sxs-lookup"><span data-stu-id="0050a-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0050a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0050a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0050a-105">参数</span><span class="sxs-lookup"><span data-stu-id="0050a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0050a-106">中`mdTypedef`实现类的标记。</span><span class="sxs-lookup"><span data-stu-id="0050a-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="0050a-107">中`mdMethodDef` `mdMemberRef` 代码主体的或标记。</span><span class="sxs-lookup"><span data-stu-id="0050a-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="0050a-108">中`mdMethodDef` `mdMemberRef` 要实现的接口方法的或标记。</span><span class="sxs-lookup"><span data-stu-id="0050a-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0050a-109">要求</span><span class="sxs-lookup"><span data-stu-id="0050a-109">Requirements</span></span>  
 <span data-ttu-id="0050a-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0050a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0050a-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="0050a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0050a-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0050a-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0050a-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0050a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0050a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0050a-114">See also</span></span>

- [<span data-ttu-id="0050a-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="0050a-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="0050a-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="0050a-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
