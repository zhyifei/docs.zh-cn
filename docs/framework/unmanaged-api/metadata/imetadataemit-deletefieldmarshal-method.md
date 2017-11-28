---
title: "IMetaDataEmit::DeleteFieldMarshal 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeleteFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f66307a2589a824db0f8ce9dca737e6b201dad59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="77719-102">IMetaDataEmit::DeleteFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="77719-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="77719-103">销毁 PInvoke 封送处理指定标记所引用的对象的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="77719-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77719-104">语法</span><span class="sxs-lookup"><span data-stu-id="77719-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77719-105">参数</span><span class="sxs-lookup"><span data-stu-id="77719-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="77719-106">[in]`mdFieldDef`或`mdParamDef`表示字段或要为其删除的封送处理的元数据签名的参数的令牌。</span><span class="sxs-lookup"><span data-stu-id="77719-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77719-107">要求</span><span class="sxs-lookup"><span data-stu-id="77719-107">Requirements</span></span>  
 <span data-ttu-id="77719-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77719-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77719-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77719-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77719-110">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="77719-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77719-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77719-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77719-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77719-112">See Also</span></span>  
 [<span data-ttu-id="77719-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="77719-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="77719-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="77719-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
