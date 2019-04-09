---
title: IMetaDataEmit::DeleteToken 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d85fb62936678f830ca7eaf26a97c36be5f23ac8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138237"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="cc237-102">IMetaDataEmit::DeleteToken 方法</span><span class="sxs-lookup"><span data-stu-id="cc237-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="cc237-103">从当前的元数据范围中删除指定的标记。</span><span class="sxs-lookup"><span data-stu-id="cc237-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc237-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc237-104">Syntax</span></span>  
  
```  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc237-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc237-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="cc237-106">[in]要删除的标记。</span><span class="sxs-lookup"><span data-stu-id="cc237-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc237-107">要求</span><span class="sxs-lookup"><span data-stu-id="cc237-107">Requirements</span></span>  
 <span data-ttu-id="cc237-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc237-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc237-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cc237-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc237-110">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cc237-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cc237-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="cc237-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc237-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc237-112">See also</span></span>

- [<span data-ttu-id="cc237-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="cc237-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cc237-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="cc237-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
