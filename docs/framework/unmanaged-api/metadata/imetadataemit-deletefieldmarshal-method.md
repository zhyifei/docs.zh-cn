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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7ba2d6f143b6bbb9ddc5a056191e53f719bfeb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643944"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="ee9bf-102">IMetaDataEmit::DeleteFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="ee9bf-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="ee9bf-103">销毁 PInvoke 封送处理指定的标记所引用的对象的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="ee9bf-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee9bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee9bf-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee9bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee9bf-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ee9bf-106">[in]`mdFieldDef`或`mdParamDef`表示字段或参数为要从中删除的封送处理的元数据签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="ee9bf-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee9bf-107">要求</span><span class="sxs-lookup"><span data-stu-id="ee9bf-107">Requirements</span></span>  
 <span data-ttu-id="ee9bf-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee9bf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee9bf-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee9bf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee9bf-110">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ee9bf-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee9bf-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee9bf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee9bf-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee9bf-112">See also</span></span>
- [<span data-ttu-id="ee9bf-113">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="ee9bf-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ee9bf-114">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="ee9bf-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
