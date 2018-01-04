---
title: "IObjectHandle::Unwrap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IObjectHandle.Unwrap
api_location: mscoree.dll
api_type: COM
f1_keywords: Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b14483279e4416c898a836ae87c6bca180b4736
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="0136c-102">IObjectHandle::Unwrap 方法</span><span class="sxs-lookup"><span data-stu-id="0136c-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="0136c-103">解包中间接寻址的封送按值对象。</span><span class="sxs-lookup"><span data-stu-id="0136c-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0136c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0136c-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0136c-105">参数</span><span class="sxs-lookup"><span data-stu-id="0136c-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="0136c-106">[out]指向要为解包的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="0136c-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0136c-107">惠?</span><span class="sxs-lookup"><span data-stu-id="0136c-107">Requirements</span></span>  
 <span data-ttu-id="0136c-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0136c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0136c-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0136c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0136c-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0136c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0136c-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0136c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0136c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0136c-112">See Also</span></span>  
 
