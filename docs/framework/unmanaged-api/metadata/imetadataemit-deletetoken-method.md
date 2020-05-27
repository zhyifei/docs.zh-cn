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
ms.openlocfilehash: 78f3ea0d84c932732a752f3af2dc952100fef831
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009270"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="ff115-102">IMetaDataEmit::DeleteToken 方法</span><span class="sxs-lookup"><span data-stu-id="ff115-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="ff115-103">从当前的元数据范围中删除指定的标记。</span><span class="sxs-lookup"><span data-stu-id="ff115-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff115-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff115-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff115-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff115-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="ff115-106">中要删除的标记。</span><span class="sxs-lookup"><span data-stu-id="ff115-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff115-107">要求</span><span class="sxs-lookup"><span data-stu-id="ff115-107">Requirements</span></span>  
 <span data-ttu-id="ff115-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff115-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff115-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ff115-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff115-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ff115-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff115-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff115-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff115-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff115-112">See also</span></span>

- [<span data-ttu-id="ff115-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="ff115-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ff115-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="ff115-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
