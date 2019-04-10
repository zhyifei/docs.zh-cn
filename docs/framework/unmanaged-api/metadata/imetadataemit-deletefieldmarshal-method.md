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
ms.openlocfilehash: 78f2405bba9172b775b01e5417860c3f3d2dd4a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206923"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="eb6e2-102">IMetaDataEmit::DeleteFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="eb6e2-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="eb6e2-103">销毁 PInvoke 封送处理指定的标记所引用的对象的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb6e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb6e2-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb6e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb6e2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="eb6e2-106">[in]`mdFieldDef`或`mdParamDef`表示字段或参数为要从中删除的封送处理的元数据签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb6e2-107">要求</span><span class="sxs-lookup"><span data-stu-id="eb6e2-107">Requirements</span></span>  
 <span data-ttu-id="eb6e2-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6e2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb6e2-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb6e2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb6e2-110">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eb6e2-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="eb6e2-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="eb6e2-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eb6e2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb6e2-112">See also</span></span>

- [<span data-ttu-id="eb6e2-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="eb6e2-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="eb6e2-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="eb6e2-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
