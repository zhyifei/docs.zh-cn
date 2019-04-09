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
ms.openlocfilehash: a195daf2aa1b1c5a8f9c4335f7c4185f30093360
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178524"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="1626c-102">IMetaDataEmit::DeleteClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="1626c-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="1626c-103">销毁指定的标记所表示的类型的类布局的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="1626c-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1626c-104">语法</span><span class="sxs-lookup"><span data-stu-id="1626c-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1626c-105">参数</span><span class="sxs-lookup"><span data-stu-id="1626c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1626c-106">[in]`mdTypeDef`元数据标记所表示的类型将为其删除的类布局。</span><span class="sxs-lookup"><span data-stu-id="1626c-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1626c-107">要求</span><span class="sxs-lookup"><span data-stu-id="1626c-107">Requirements</span></span>  
 <span data-ttu-id="1626c-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1626c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1626c-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1626c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1626c-110">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1626c-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1626c-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="1626c-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1626c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1626c-112">See also</span></span>

- [<span data-ttu-id="1626c-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="1626c-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1626c-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="1626c-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
