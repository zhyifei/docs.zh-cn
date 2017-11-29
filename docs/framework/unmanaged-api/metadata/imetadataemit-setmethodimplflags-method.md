---
title: "IMetaDataEmit::SetMethodImplFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetMethodImplFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d69940d5cffe397d009b7364a20a09dbbd95db4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="d9d66-102">IMetaDataEmit::SetMethodImplFlags 方法</span><span class="sxs-lookup"><span data-stu-id="d9d66-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="d9d66-103">设置或更新由指定标记引用的继承的方法实现的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="d9d66-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d66-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9d66-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9d66-105">参数</span><span class="sxs-lookup"><span data-stu-id="d9d66-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="d9d66-106">[in]要更改方法的标记。</span><span class="sxs-lookup"><span data-stu-id="d9d66-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="d9d66-107">[in]值的组合[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举，指定方法实现功能。</span><span class="sxs-lookup"><span data-stu-id="d9d66-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9d66-108">要求</span><span class="sxs-lookup"><span data-stu-id="d9d66-108">Requirements</span></span>  
 <span data-ttu-id="d9d66-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9d66-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9d66-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9d66-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9d66-111">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d9d66-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9d66-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9d66-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d66-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9d66-113">See Also</span></span>  
 [<span data-ttu-id="d9d66-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d9d66-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="d9d66-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="d9d66-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
