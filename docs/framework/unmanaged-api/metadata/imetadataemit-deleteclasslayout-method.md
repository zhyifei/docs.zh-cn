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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 663f2de5acb3aac92c29a19f5f5db16b5355fe89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444778"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="be801-102">IMetaDataEmit::DeleteClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="be801-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="be801-103">销毁指定标记所表示的类型的类布局元数据签名。</span><span class="sxs-lookup"><span data-stu-id="be801-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be801-104">语法</span><span class="sxs-lookup"><span data-stu-id="be801-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be801-105">参数</span><span class="sxs-lookup"><span data-stu-id="be801-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="be801-106">[in]`mdTypeDef`表示类布局将删除为其类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="be801-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be801-107">要求</span><span class="sxs-lookup"><span data-stu-id="be801-107">Requirements</span></span>  
 <span data-ttu-id="be801-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be801-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be801-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be801-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be801-110">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="be801-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be801-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be801-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be801-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="be801-112">See Also</span></span>  
 [<span data-ttu-id="be801-113">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="be801-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="be801-114">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="be801-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
