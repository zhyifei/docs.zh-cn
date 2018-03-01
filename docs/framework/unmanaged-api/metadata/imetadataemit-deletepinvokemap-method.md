---
title: "IMetaDataEmit::DeletePinvokeMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1479c3fb19feec0e42ee4aec8544a35ce51350a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="50004-102">IMetaDataEmit::DeletePinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="50004-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="50004-103">销毁指定标记所引用的对象的 PInvoke 映射元数据。</span><span class="sxs-lookup"><span data-stu-id="50004-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50004-104">语法</span><span class="sxs-lookup"><span data-stu-id="50004-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50004-105">参数</span><span class="sxs-lookup"><span data-stu-id="50004-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="50004-106">[in]`mdFieldDef`或`mdMethodDef`表示要为其删除 PInvoke 映射元数据对象的令牌。</span><span class="sxs-lookup"><span data-stu-id="50004-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50004-107">惠?</span><span class="sxs-lookup"><span data-stu-id="50004-107">Requirements</span></span>  
 <span data-ttu-id="50004-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50004-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50004-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50004-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50004-110">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="50004-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50004-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50004-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50004-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="50004-112">See Also</span></span>  
 [<span data-ttu-id="50004-113">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="50004-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="50004-114">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="50004-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
