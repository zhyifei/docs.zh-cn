---
title: IMetaDataEmit::DeletePinvokeMap 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 79af7b5679598ffa82471dcb69adabc2394b13fa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009296"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="7b568-102">IMetaDataEmit::DeletePinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="7b568-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="7b568-103">销毁指定标记所引用的对象的 PInvoke 映射元数据。</span><span class="sxs-lookup"><span data-stu-id="7b568-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b568-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b568-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b568-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b568-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7b568-106">中`mdFieldDef`或 `mdMethodDef` 标记，它表示要为其删除 PInvoke 映射元数据的对象。</span><span class="sxs-lookup"><span data-stu-id="7b568-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b568-107">要求</span><span class="sxs-lookup"><span data-stu-id="7b568-107">Requirements</span></span>  
 <span data-ttu-id="7b568-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b568-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b568-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="7b568-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b568-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7b568-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b568-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b568-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b568-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b568-112">See also</span></span>

- [<span data-ttu-id="7b568-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="7b568-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7b568-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="7b568-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
