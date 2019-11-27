---
title: IMetaDataEmit::DeleteFieldMarshal 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 652169c67461c1663c005dd014290c4cf2d993ba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434365"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="5d975-102">IMetaDataEmit::DeleteFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="5d975-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="5d975-103">销毁指定标记所引用的对象的 PInvoke 封送元数据签名。</span><span class="sxs-lookup"><span data-stu-id="5d975-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d975-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d975-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d975-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d975-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5d975-106">中一个 `mdFieldDef` 或 `mdParamDef` 标记，它表示要删除封送处理元数据签名的字段或参数。</span><span class="sxs-lookup"><span data-stu-id="5d975-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d975-107">要求</span><span class="sxs-lookup"><span data-stu-id="5d975-107">Requirements</span></span>  
 <span data-ttu-id="5d975-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d975-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d975-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5d975-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d975-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5d975-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d975-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d975-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d975-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d975-112">See also</span></span>

- [<span data-ttu-id="5d975-113">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="5d975-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5d975-114">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="5d975-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
