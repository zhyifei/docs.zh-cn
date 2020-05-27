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
ms.openlocfilehash: 6d0f9a8c5c3baf7594e098a3d5544bad55fdc917
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009283"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="b2e40-102">IMetaDataEmit::DeleteFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="b2e40-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="b2e40-103">销毁指定标记所引用的对象的 PInvoke 封送元数据签名。</span><span class="sxs-lookup"><span data-stu-id="b2e40-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e40-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2e40-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2e40-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2e40-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b2e40-106">中`mdFieldDef`或 `mdParamDef` 标记，它表示要删除封送处理元数据签名的字段或参数。</span><span class="sxs-lookup"><span data-stu-id="b2e40-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2e40-107">要求</span><span class="sxs-lookup"><span data-stu-id="b2e40-107">Requirements</span></span>  
 <span data-ttu-id="b2e40-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2e40-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2e40-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b2e40-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2e40-110">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b2e40-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2e40-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2e40-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e40-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2e40-112">See also</span></span>

- [<span data-ttu-id="b2e40-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="b2e40-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b2e40-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="b2e40-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
