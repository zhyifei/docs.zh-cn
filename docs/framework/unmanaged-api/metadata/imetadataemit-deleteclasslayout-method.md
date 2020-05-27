---
title: IMetaDataEmit::DeleteClassLayout 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: 3ef6b89ed6578d77f30d5e53657b962b200b0ed6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009310"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="a8860-102">IMetaDataEmit::DeleteClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="a8860-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="a8860-103">销毁由指定标记表示的类型的类布局元数据签名。</span><span class="sxs-lookup"><span data-stu-id="a8860-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8860-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8860-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8860-105">参数</span><span class="sxs-lookup"><span data-stu-id="a8860-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a8860-106">中一个 `mdTypeDef` 元数据标记，它表示将删除类布局的类型。</span><span class="sxs-lookup"><span data-stu-id="a8860-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8860-107">要求</span><span class="sxs-lookup"><span data-stu-id="a8860-107">Requirements</span></span>  
 <span data-ttu-id="a8860-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8860-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8860-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a8860-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8860-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a8860-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8860-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8860-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8860-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8860-112">See also</span></span>

- [<span data-ttu-id="a8860-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="a8860-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a8860-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="a8860-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
