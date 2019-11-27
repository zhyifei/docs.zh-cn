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
ms.openlocfilehash: 1621e955795fcdbb651114c60eb6a1126a23d037
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434359"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="9ddb1-102">IMetaDataEmit::DeletePinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="9ddb1-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="9ddb1-103">销毁指定标记所引用的对象的 PInvoke 映射元数据。</span><span class="sxs-lookup"><span data-stu-id="9ddb1-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ddb1-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ddb1-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ddb1-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ddb1-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9ddb1-106">中一个 `mdFieldDef` 或 `mdMethodDef` 标记，它表示要为其删除 PInvoke 映射元数据的对象。</span><span class="sxs-lookup"><span data-stu-id="9ddb1-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ddb1-107">要求</span><span class="sxs-lookup"><span data-stu-id="9ddb1-107">Requirements</span></span>  
 <span data-ttu-id="9ddb1-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ddb1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ddb1-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="9ddb1-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ddb1-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9ddb1-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ddb1-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddb1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddb1-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ddb1-112">See also</span></span>

- [<span data-ttu-id="9ddb1-113">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="9ddb1-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9ddb1-114">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="9ddb1-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
